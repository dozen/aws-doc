[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 register-image:


**************
register-image
**************



===========
Description
===========



Registers an AMI. When you're creating an AMI, this is the final step you must complete before you can launch an instance from the AMI. For more information about creating AMIs, see `Creating Your Own AMIs <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

.. note::

   

  For Amazon EBS-backed instances,  create-image creates and registers the AMI in a single request, so you don't have to register the AMI yourself.

   

 

You can also use ``register-image`` to create an Amazon EBS-backed Linux AMI from a snapshot of a root device volume. You specify the snapshot using the block device mapping. For more information, see `Launching a Linux Instance from a Backup <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-launch-snapshot.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

You can't register an image where a secondary (non-root) snapshot has AWS Marketplace product codes.

 

Some Linux distributions, such as Red Hat Enterprise Linux (RHEL) and SUSE Linux Enterprise Server (SLES), use the EC2 billing product code associated with an AMI to verify the subscription status for package updates. Creating an AMI from an EBS snapshot does not maintain this billing code, and subsequent instances launched from such an AMI will not be able to connect to package update infrastructure. To create an AMI that must retain billing codes, see  create-image .

 

If needed, you can deregister an AMI at any time. Any modifications you make to an AMI backed by an instance store volume invalidates its registration. If you make changes to an image, deregister the previous image and register the new image.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/RegisterImage>`_


========
Synopsis
========

::

    register-image
  [--image-location <value>]
  [--architecture <value>]
  [--block-device-mappings <value>]
  [--description <value>]
  [--dry-run | --no-dry-run]
  [--ena-support | --no-ena-support]
  [--kernel-id <value>]
  --name <value>
  [--billing-products <value>]
  [--ramdisk-id <value>]
  [--root-device-name <value>]
  [--sriov-net-support <value>]
  [--virtualization-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--image-location`` (string)


  The full path to your AMI manifest in Amazon S3 storage.

  

``--architecture`` (string)


  The architecture of the AMI.

   

  Default: For Amazon EBS-backed AMIs, ``i386`` . For instance store-backed AMIs, the architecture specified in the manifest file.

  

  Possible values:

  
  *   ``i386``

  
  *   ``x86_64``

  

  

``--block-device-mappings`` (list)


  One or more block device mapping entries.

  



Shorthand Syntax::

    DeviceName=string,VirtualName=string,Ebs={Encrypted=boolean,DeleteOnTermination=boolean,Iops=integer,SnapshotId=string,VolumeSize=integer,VolumeType=string},NoDevice=string ...




JSON Syntax::

  [
    {
      "DeviceName": "string",
      "VirtualName": "string",
      "Ebs": {
        "Encrypted": true|false,
        "DeleteOnTermination": true|false,
        "Iops": integer,
        "SnapshotId": "string",
        "VolumeSize": integer,
        "VolumeType": "standard"|"io1"|"gp2"|"sc1"|"st1"
      },
      "NoDevice": "string"
    }
    ...
  ]



``--description`` (string)


  A description for your AMI.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--ena-support`` | ``--no-ena-support`` (boolean)


  Set to ``true`` to enable enhanced networking with ENA for the AMI and any instances that you launch from the AMI.

   

  This option is supported only for HVM AMIs. Specifying this option with a PV AMI can make instances launched from the AMI unreachable.

  

``--kernel-id`` (string)


  The ID of the kernel.

  

``--name`` (string)


  A name for your AMI.

   

  Constraints: 3-128 alphanumeric characters, parentheses (()), square brackets ([]), spaces ( ), periods (.), slashes (/), dashes (-), single quotes ('), at-signs (@), or underscores(_)

  

``--billing-products`` (list)


  The billing product codes. Your account must be authorized to specify billing product codes. Otherwise, you can use the AWS Marketplace to bill for the use of an AMI.

  



Syntax::

  "string" "string" ...



``--ramdisk-id`` (string)


  The ID of the RAM disk.

  

``--root-device-name`` (string)


  The name of the root device (for example, ``/dev/sda1`` , or ``/dev/xvda`` ).

  

``--sriov-net-support`` (string)


  Set to ``simple`` to enable enhanced networking with the Intel 82599 Virtual Function interface for the AMI and any instances that you launch from the AMI.

   

  There is no way to disable ``sriovNetSupport`` at this time.

   

  This option is supported only for HVM AMIs. Specifying this option with a PV AMI can make instances launched from the AMI unreachable.

  

``--virtualization-type`` (string)


  The type of virtualization.

   

  Default: ``paravirtual``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To register an AMI using a manifest file**

This example registers an AMI using the specified manifest file in Amazon S3.

Command::

  aws ec2 register-image --image-location my-s3-bucket/myimage/image.manifest.xml --name "MyImage"

Output::

  {
      "ImageId": "ami-61341708"
  }

**To add a block device mapping**

Add the following parameter to your ``register-image`` command to add an Amazon EBS volume with the device name ``/dev/sdh`` and a volume size of 100::

  --block-device-mappings "[{\"DeviceName\": \"/dev/sdh\",\"Ebs\":{\"VolumeSize\":100}}]"

Add the following parameter to your ``register-image`` command to add ``ephemeral1`` as an instance store volume with the device name ``/dev/sdc``::

  --block-device-mappings "[{\"DeviceName\": \"/dev/sdc\",\"VirtualName\":\"ephemeral1\"}]"

Add the following parameter to your ``register-image`` command to omit a device (for example, ``/dev/sdf``)::

  --block-device-mappings "[{\"DeviceName\": \"/dev/sdf\",\"NoDevice\":\"\"}]"


======
Output
======

ImageId -> (string)

  

  The ID of the newly registered AMI.

  

  

