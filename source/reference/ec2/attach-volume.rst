[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 attach-volume:


*************
attach-volume
*************



===========
Description
===========



Attaches an EBS volume to a running or stopped instance and exposes it to the instance with the specified device name.

 

Encrypted EBS volumes may only be attached to instances that support Amazon EBS encryption. For more information, see `Amazon EBS Encryption`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

For a list of supported device names, see `Attaching an EBS Volume to an Instance`_ . Any device names that aren't reserved for instance store volumes can be used for EBS volumes. For more information, see `Amazon EC2 Instance Store`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

If a volume has an AWS Marketplace product code:

 

 
* The volume can be attached only to a stopped instance.
 
* AWS Marketplace product codes are copied from the volume to the instance.
 
* You must be subscribed to the product.
 
* The instance type and operating system of the instance must support the product. For example, you can't detach a volume from a Windows instance and attach it to a Linux instance.
 

 

For an overview of the AWS Marketplace, see `Introducing AWS Marketplace`_ .

 

For more information about EBS volumes, see `Attaching Amazon EBS Volumes`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    attach-volume
  [--dry-run | --no-dry-run]
  --volume-id <value>
  --instance-id <value>
  --device <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--volume-id`` (string)


  The ID of the EBS volume. The volume and instance must be within the same Availability Zone.

  

``--instance-id`` (string)


  The ID of the instance.

  

``--device`` (string)


  The device name to expose to the instance (for example, ``/dev/sdh`` or ``xvdh`` ).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To attach a volume to an instance**

This example command attaches a volume (``vol-1234abcd``) to an instance (``i-abcd1234``) as ``/dev/sdf``.

Command::

  aws ec2 attach-volume --volume-id vol-1234abcd --instance-id i-abcd1234 --device /dev/sdf

Output::

   {
       "AttachTime": "YYYY-MM-DDTHH:MM:SS.000Z",
       "InstanceId": "i-abcd1234",
       "VolumeId": "vol-1234abcd",
       "State": "attaching",
       "Device": "/dev/sdf"
   }


======
Output
======

VolumeId -> (string)

  

  The ID of the volume.

  

  

InstanceId -> (string)

  

  The ID of the instance.

  

  

Device -> (string)

  

  The device name.

  

  

State -> (string)

  

  The attachment state of the volume.

  

  

AttachTime -> (timestamp)

  

  The time stamp when the attachment initiated.

  

  

DeleteOnTermination -> (boolean)

  

  Indicates whether the EBS volume is deleted on instance termination.

  

  



.. _Amazon EC2 Instance Store: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html
.. _Attaching Amazon EBS Volumes: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-attaching-volume.html
.. _Attaching an EBS Volume to an Instance: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-attaching-volume.html
.. _Amazon EBS Encryption: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html
.. _Introducing AWS Marketplace: https://aws.amazon.com/marketplace/help/200900000
