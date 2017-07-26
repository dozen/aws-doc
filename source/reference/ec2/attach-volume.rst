[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 attach-volume:


*************
attach-volume
*************



===========
Description
===========



Attaches an EBS volume to a running or stopped instance and exposes it to the instance with the specified device name.

 

Encrypted EBS volumes may only be attached to instances that support Amazon EBS encryption. For more information, see `Amazon EBS Encryption <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

For a list of supported device names, see `Attaching an EBS Volume to an Instance <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-attaching-volume.html>`_ . Any device names that aren't reserved for instance store volumes can be used for EBS volumes. For more information, see `Amazon EC2 Instance Store <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

If a volume has an AWS Marketplace product code:

 

 
* The volume can be attached only to a stopped instance. 
 
* AWS Marketplace product codes are copied from the volume to the instance. 
 
* You must be subscribed to the product. 
 
* The instance type and operating system of the instance must support the product. For example, you can't detach a volume from a Windows instance and attach it to a Linux instance. 
 

 

For an overview of the AWS Marketplace, see `Introducing AWS Marketplace <https://aws.amazon.com/marketplace/help/200900000>`_ .

 

For more information about EBS volumes, see `Attaching Amazon EBS Volumes <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-attaching-volume.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AttachVolume>`_


========
Synopsis
========

::

    attach-volume
  --device <value>
  --instance-id <value>
  --volume-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--device`` (string)


  The device name to expose to the instance (for example, ``/dev/sdh`` or ``xvdh`` ).

  

``--instance-id`` (string)


  The ID of the instance.

  

``--volume-id`` (string)


  The ID of the EBS volume. The volume and instance must be within the same Availability Zone.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attach a volume to an instance**

This example command attaches a volume (``vol-1234567890abcdef0``) to an instance (``i-01474ef662b89480``) as ``/dev/sdf``.

Command::

  aws ec2 attach-volume --volume-id vol-1234567890abcdef0 --instance-id i-01474ef662b89480 --device /dev/sdf

Output::

   {
       "AttachTime": "YYYY-MM-DDTHH:MM:SS.000Z",
       "InstanceId": "i-01474ef662b89480",
       "VolumeId": "vol-1234567890abcdef0",
       "State": "attaching",
       "Device": "/dev/sdf"
   }


======
Output
======

AttachTime -> (timestamp)

  

  The time stamp when the attachment initiated.

  

  

Device -> (string)

  

  The device name.

  

  

InstanceId -> (string)

  

  The ID of the instance.

  

  

State -> (string)

  

  The attachment state of the volume.

  

  

VolumeId -> (string)

  

  The ID of the volume.

  

  

DeleteOnTermination -> (boolean)

  

  Indicates whether the EBS volume is deleted on instance termination.

  

  

