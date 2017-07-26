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

 

For more information, see `Creating Amazon EBS-Backed Linux AMIs <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami-ebs.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateImage>`_


========
Synopsis
========

::

    create-image
  [--block-device-mappings <value>]
  [--description <value>]
  [--dry-run | --no-dry-run]
  --instance-id <value>
  --name <value>
  [--no-reboot | --reboot]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--block-device-mappings`` (list)


  Information about one or more block device mappings.

  



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


  A description for the new image.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the instance.

  

``--name`` (string)


  A name for the new image.

   

  Constraints: 3-128 alphanumeric characters, parentheses (()), square brackets ([]), spaces ( ), periods (.), slashes (/), dashes (-), single quotes ('), at-signs (@), or underscores(_)

  

``--no-reboot`` | ``--reboot`` (boolean)


  By default, Amazon EC2 attempts to shut down and reboot the instance before creating the image. If the 'No Reboot' option is set, Amazon EC2 doesn't shut down the instance before creating the image. When this option is used, file system integrity on the created image can't be guaranteed.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an AMI from an Amazon EBS-backed instance**

This example creates an AMI from the specified instance.

Command::

  aws ec2 create-image --instance-id i-1234567890abcdef0 --name "My server" --description "An AMI for my server"

Output::

  {
      "ImageId": "ami-5731123e"
  }

This example creates an AMI and sets the --no-reboot parameter, so that the instance is not rebooted before the image is created.

Command::

  aws ec2 create-image --instance-id i-0b09a25c58929de26 --name "My server" --no-reboot

Output::

  {
    "ImageId": "ami-1a2b3c4d"
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

  

  

