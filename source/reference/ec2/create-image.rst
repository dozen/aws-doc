[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-image:


************
create-image
************



===========
Description
===========



Creates an Amazon EBS-backed AMI from an Amazon EBS-backed instance that is either running or stopped.

 

If you customized your instance with instance store volumes or EBS volumes in addition to the root device volume, the new AMI contains block device mapping information for those volumes. When you launch an instance from this new AMI, the instance automatically launches with those additional volumes.

 

For more information, see `Creating Amazon EBS-Backed Linux AMIs`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    create-image
  [--dry-run | --no-dry-run]
  --instance-id <value>
  --name <value>
  [--description <value>]
  [--no-reboot | --reboot]
  [--block-device-mappings <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the instance.

  

``--name`` (string)


  A name for the new image.

   

  Constraints: 3-128 alphanumeric characters, parentheses (()), square brackets ([]), spaces ( ), periods (.), slashes (/), dashes (-), single quotes ('), at-signs (@), or underscores(_)

  

``--description`` (string)


  A description for the new image.

  

``--no-reboot`` | ``--reboot`` (boolean)


  By default, this parameter is set to ``false`` , which means Amazon EC2 attempts to shut down the instance cleanly before image creation and then reboots the instance. When the parameter is set to ``true`` , Amazon EC2 doesn't shut down the instance before creating the image. When this option is used, file system integrity on the created image can't be guaranteed.

  

``--block-device-mappings`` (list)


  Information about one or more block device mappings.

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an AMI from an Amazon EBS-backed instance**

This example creates an AMI from the specified instance.

Command::

  aws ec2 create-image --instance-id i-10a64379 --name "My server" --description "An AMI for my server"

Output::

  {
      "ImageId": "ami-5731123e"
  }

**To create an AMI using a block device mapping**

Add the following parameter to your ``create-image`` command to add an Amazon EBS volume with the device name ``/dev/sdh`` and a volume size of 100::

  --block-device-mappings "[{\"DeviceName\": \"/dev/sdh\",\"Ebs\":{\"VolumeSize\":100}}]"

Add the following parameter to your ``create-image`` command to add ``ephemeral1`` as an instance store volume with the device name ``/dev/sdc``::

  --block-device-mappings "[{\"DeviceName\": \"/dev/sdc\",\"VirtualName\":\"ephemeral1\"}]"

Add the following parameter to your ``create-image`` command to omit a device included on the instance (for example, ``/dev/sdf``)::

  --block-device-mappings "[{\"DeviceName\": \"/dev/sdf\",\"NoDevice\":\"\"}]"


======
Output
======

ImageId -> (string)

  

  The ID of the new AMI.

  

  



.. _Creating Amazon EBS-Backed Linux AMIs: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami-ebs.html
