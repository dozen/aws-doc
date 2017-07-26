[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 detach-volume:


*************
detach-volume
*************



===========
Description
===========



Detaches an EBS volume from an instance. Make sure to unmount any file systems on the device within your operating system before detaching the volume. Failure to do so results in the volume being stuck in a busy state while detaching.

 

If an Amazon EBS volume is the root device of an instance, it can't be detached while the instance is running. To detach the root volume, stop the instance first.

 

When a volume with an AWS Marketplace product code is detached from an instance, the product code is no longer associated with the instance.

 

For more information, see `Detaching an Amazon EBS Volume`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    detach-volume
  [--dry-run | --no-dry-run]
  --volume-id <value>
  [--instance-id <value>]
  [--device <value>]
  [--force | --no-force]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--volume-id`` (string)


  The ID of the volume.

  

``--instance-id`` (string)


  The ID of the instance.

  

``--device`` (string)


  The device name.

  

``--force`` | ``--no-force`` (boolean)


  Forces detachment if the previous detachment attempt did not occur cleanly (for example, logging into an instance, unmounting the volume, and detaching normally). This option can lead to data loss or a corrupted file system. Use this option only as a last resort to detach a volume from a failed instance. The instance won't have an opportunity to flush file system caches or file system metadata. If you use this option, you must perform file system check and repair procedures.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To detach a volume from an instance**

This example command detaches the volume (``vol-1234abcd``) from the instance it is attached to.

Command::

  aws ec2 detach-volume --volume-id vol-1234abcd

Output::

   {
       "AttachTime": "2014-02-27T19:23:06.000Z",
       "InstanceId": "i-0751440e",
       "VolumeId": "vol-1234abcd",
       "State": "detaching",
       "Device": "/dev/sdb"
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

  

  



.. _Detaching an Amazon EBS Volume: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-detaching-volume.html
