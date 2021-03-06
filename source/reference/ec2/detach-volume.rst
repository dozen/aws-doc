[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 detach-volume:


*************
detach-volume
*************



===========
Description
===========



Detaches an EBS volume from an instance. Make sure to unmount any file systems on the device within your operating system before detaching the volume. Failure to do so can result in the volume becoming stuck in the ``busy`` state while detaching. If this happens, detachment can be delayed indefinitely until you unmount the volume, force detachment, reboot the instance, or all three. If an EBS volume is the root device of an instance, it can't be detached while the instance is running. To detach the root volume, stop the instance first.

 

When a volume with an AWS Marketplace product code is detached from an instance, the product code is no longer associated with the instance.

 

For more information, see `Detaching an Amazon EBS Volume <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-detaching-volume.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DetachVolume>`_


========
Synopsis
========

::

    detach-volume
  [--device <value>]
  [--force | --no-force]
  [--instance-id <value>]
  --volume-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--device`` (string)


  The device name.

  

``--force`` | ``--no-force`` (boolean)


  Forces detachment if the previous detachment attempt did not occur cleanly (for example, logging into an instance, unmounting the volume, and detaching normally). This option can lead to data loss or a corrupted file system. Use this option only as a last resort to detach a volume from a failed instance. The instance won't have an opportunity to flush file system caches or file system metadata. If you use this option, you must perform file system check and repair procedures.

  

``--instance-id`` (string)


  The ID of the instance.

  

``--volume-id`` (string)


  The ID of the volume.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To detach a volume from an instance**

This example command detaches the volume (``vol-049df61146c4d7901``) from the instance it is attached to.

Command::

  aws ec2 detach-volume --volume-id vol-1234567890abcdef0

Output::

   {
       "AttachTime": "2014-02-27T19:23:06.000Z",
       "InstanceId": "i-1234567890abcdef0",
       "VolumeId": "vol-049df61146c4d7901",
       "State": "detaching",
       "Device": "/dev/sdb"
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

  

  

