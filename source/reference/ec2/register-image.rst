[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 register-image:


**************
register-image
**************



===========
Description
===========



Registers an AMI. When you're creating an AMI, this is the final step you must complete before you can launch an instance from the AMI. For more information about creating AMIs, see `Creating Your Own AMIs`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

.. note::

  

  For Amazon EBS-backed instances,  create-image creates and registers the AMI in a single request, so you don't have to register the AMI yourself.

  

 

You can also use ``register-image`` to create an Amazon EBS-backed Linux AMI from a snapshot of a root device volume. For more information, see `Launching an Instance from a Snapshot`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

.. warning::

   

  Some Linux distributions, such as Red Hat Enterprise Linux (RHEL) and SUSE Linux Enterprise Server (SLES), use the EC2 ``billingProduct`` code associated with an AMI to verify subscription status for package updates. Creating an AMI from an EBS snapshot does not maintain this billing code, and subsequent instances launched from such an AMI will not be able to connect to package update infrastructure.

   

  Similarly, although you can create a Windows AMI from a snapshot, you can't successfully launch an instance from the AMI.

   

  To create Windows AMIs or to create AMIs for Linux operating systems that must retain AMI billing codes to work properly, see  create-image .

   

 

If needed, you can deregister an AMI at any time. Any modifications you make to an AMI backed by an instance store volume invalidates its registration. If you make changes to an image, deregister the previous image and register the new image.

 

.. note::

  

  You can't register an image where a secondary (non-root) snapshot has AWS Marketplace product codes.

  



========
Synopsis
========

::

    register-image
  [--dry-run | --no-dry-run]
  [--image-location <value>]
  --name <value>
  [--description <value>]
  [--architecture <value>]
  [--kernel-id <value>]
  [--ramdisk-id <value>]
  [--root-device-name <value>]
  [--block-device-mappings <value>]
  [--virtualization-type <value>]
  [--sriov-net-support <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--image-location`` (string)


  The full path to your AMI manifest in Amazon S3 storage.

  

``--name`` (string)


  A name for your AMI.

   

  Constraints: 3-128 alphanumeric characters, parentheses (()), square brackets ([]), spaces ( ), periods (.), slashes (/), dashes (-), single quotes ('), at-signs (@), or underscores(_)

  

``--description`` (string)


  A description for your AMI.

  

``--architecture`` (string)


  The architecture of the AMI.

   

  Default: For Amazon EBS-backed AMIs, ``i386`` . For instance store-backed AMIs, the architecture specified in the manifest file.

  

  Possible values:

  
  *   ``i386``

  
  *   ``x86_64``

  

  

``--kernel-id`` (string)


  The ID of the kernel.

  

``--ramdisk-id`` (string)


  The ID of the RAM disk.

  

``--root-device-name`` (string)


  The name of the root device (for example, ``/dev/sda1`` , or ``/dev/xvda`` ).

  

``--block-device-mappings`` (list)


  One or more block device mapping entries.

  



Shorthand Syntax::

    VirtualName=string,DeviceName=string,Ebs={SnapshotId=string,VolumeSize=integer,DeleteOnTermination=boolean,VolumeType=string,Iops=integer,Encrypted=boolean},NoDevice=string ...




JSON Syntax::

  [
    {
      "VirtualName": "string",
      "DeviceName": "string",
      "Ebs": {
        "SnapshotId": "string",
        "VolumeSize": integer,
        "DeleteOnTermination": true|false,
        "VolumeType": "standard"|"io1"|"gp2",
        "Iops": integer,
        "Encrypted": true|false
      },
      "NoDevice": "string"
    }
    ...
  ]



``--virtualization-type`` (string)


  The type of virtualization.

   

  Default: ``paravirtual`` 

  

``--sriov-net-support`` (string)


  Set to ``simple`` to enable enhanced networking for the AMI and any instances that you launch from the AMI.

   

  There is no way to disable enhanced networking at this time.

   

  This option is supported only for HVM AMIs. Specifying this option with a PV AMI can make instances launched from the AMI unreachable.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  



.. _Creating Your Own AMIs: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami.html
.. _Launching an Instance from a Snapshot: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_LaunchingInstanceFromSnapshot.html
