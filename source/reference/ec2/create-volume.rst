[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-volume:


*************
create-volume
*************



===========
Description
===========



Creates an EBS volume that can be attached to an instance in the same Availability Zone. The volume is created in the regional endpoint that you send the HTTP request to. For more information see `Regions and Endpoints`_ .

 

You can create a new empty volume or restore a volume from an EBS snapshot. Any AWS Marketplace product codes from the snapshot are propagated to the volume.

 

You can create encrypted volumes with the ``Encrypted`` parameter. Encrypted volumes may only be attached to instances that support Amazon EBS encryption. Volumes that are created from encrypted snapshots are also automatically encrypted. For more information, see `Amazon EBS Encryption`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

For more information, see `Creating or Restoring an Amazon EBS Volume`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    create-volume
  [--dry-run | --no-dry-run]
  [--size <value>]
  [--snapshot-id <value>]
  --availability-zone <value>
  [--volume-type <value>]
  [--iops <value>]
  [--encrypted | --no-encrypted]
  [--kms-key-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--size`` (integer)


  The size of the volume, in GiBs.

   

  Constraints: ``1-1024`` for ``standard`` volumes, ``1-16384`` for ``gp2`` volumes, and ``4-16384`` for ``io1`` volumes. If you specify a snapshot, the volume size must be equal to or larger than the snapshot size.

   

  Default: If you're creating the volume from a snapshot and don't specify a volume size, the default is the snapshot size.

  

``--snapshot-id`` (string)


  The snapshot from which to create the volume.

  

``--availability-zone`` (string)


  The Availability Zone in which to create the volume. Use  describe-availability-zones to list the Availability Zones that are currently available to you.

  

``--volume-type`` (string)


  The volume type. This can be ``gp2`` for General Purpose (SSD) volumes, ``io1`` for Provisioned IOPS (SSD) volumes, or ``standard`` for Magnetic volumes.

   

  Default: ``standard`` 

  

  Possible values:

  
  *   ``standard``

  
  *   ``io1``

  
  *   ``gp2``

  

  

``--iops`` (integer)


  Only valid for Provisioned IOPS (SSD) volumes. The number of I/O operations per second (IOPS) to provision for the volume, with a maximum ratio of 30 IOPS/GiB.

   

  Constraint: Range is 100 to 20000 for Provisioned IOPS (SSD) volumes 

  

``--encrypted`` | ``--no-encrypted`` (boolean)


  Specifies whether the volume should be encrypted. Encrypted Amazon EBS volumes may only be attached to instances that support Amazon EBS encryption. Volumes that are created from encrypted snapshots are automatically encrypted. There is no way to create an encrypted volume from an unencrypted snapshot or vice versa. If your AMI uses encrypted volumes, you can only launch it on supported instance types. For more information, see `Amazon EBS Encryption`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--kms-key-id`` (string)


  The full ARN of the AWS Key Management Service (AWS KMS) customer master key (CMK) to use when creating the encrypted volume. This parameter is only required if you want to use a non-default CMK; if this parameter is not specified, the default CMK for EBS is used. The ARN contains the ``arn:aws:kms`` namespace, followed by the region of the CMK, the AWS account ID of the CMK owner, the ``key`` namespace, and then the CMK ID. For example, arn:aws:kms:*us-east-1* :*012345678910* :key/*abcd1234-a123-456a-a12b-a123b4cd56ef* . If a ``KmsKeyId`` is specified, the ``Encrypted`` flag must also be set.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a new volume**

This example command creates an 80 GiB General Purpose (SSD) volume in the Availability Zone ``us-east-1a``.

Command::

  aws ec2 create-volume --size 80 --region us-east-1 --availability-zone us-east-1a --volume-type gp2

Output::

   {
       "AvailabilityZone": "us-east-1a",
       "Attachments": [],
       "Tags": [],
       "VolumeType": "gp2",
       "VolumeId": "vol-1234abcd",
       "State": "creating",
       "SnapshotId": null,
       "CreateTime": "YYYY-MM-DDTHH:MM:SS.000Z",
       "Size": 80
   }

**To create a new Provisioned IOPS (SSD) volume from a snapshot**

This example command creates a new Provisioned IOPS (SSD) volume with 1000 provisioned IOPS from a snapshot in the Availability Zone ``us-east-1a``.

Command::

  aws ec2 create-volume --region us-east-1 --availability-zone us-east-1a --snapshot-id snap-abcd1234 --volume-type io1 --iops 1000

Output::

   {
       "AvailabilityZone": "us-east-1a",
       "Attachments": [],
       "Tags": [],
       "VolumeType": "io1",
       "VolumeId": "vol-1234abcd",
       "State": "creating",
       "Iops": 1000,
       "SnapshotId": "snap-abcd1234",
       "CreateTime": "YYYY-MM-DDTHH:MM:SS.000Z",
       "Size": 500
   }


======
Output
======

VolumeId -> (string)

  

  The ID of the volume.

  

  

Size -> (integer)

  

  The size of the volume, in GiBs.

  

  

SnapshotId -> (string)

  

  The snapshot from which the volume was created, if applicable.

  

  

AvailabilityZone -> (string)

  

  The Availability Zone for the volume.

  

  

State -> (string)

  

  The volume state.

  

  

CreateTime -> (timestamp)

  

  The time stamp when volume creation was initiated.

  

  

Attachments -> (list)

  

  Information about the volume attachments.

  

  (structure)

    

    Describes volume attachment details.

    

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

      

      

    

  

Tags -> (list)

  

  Any tags assigned to the volume.

  

  (structure)

    

    Describes a tag.

    

    Key -> (string)

      

      The key of the tag. 

       

      Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

      

      

    Value -> (string)

      

      The value of the tag.

       

      Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

      

      

    

  

VolumeType -> (string)

  

  The volume type. This can be ``gp2`` for General Purpose (SSD) volumes, ``io1`` for Provisioned IOPS (SSD) volumes, or ``standard`` for Magnetic volumes.

  

  

Iops -> (integer)

  

  The number of I/O operations per second (IOPS) that the volume supports. For Provisioned IOPS (SSD) volumes, this represents the number of IOPS that are provisioned for the volume. For General Purpose (SSD) volumes, this represents the baseline performance of the volume and the rate at which the volume accumulates I/O credits for bursting. For more information on General Purpose (SSD) baseline performance, I/O credits, and bursting, see `Amazon EBS Volume Types`_ in the *Amazon Elastic Compute Cloud User Guide* .

   

  Constraint: Range is 100 to 20000 for Provisioned IOPS (SSD) volumes and 3 to 10000 for General Purpose (SSD) volumes.

   

  Condition: This parameter is required for requests to create ``io1`` volumes; it is not used in requests to create ``standard`` or ``gp2`` volumes.

  

  

Encrypted -> (boolean)

  

  Indicates whether the volume will be encrypted.

  

  

KmsKeyId -> (string)

  

  The full ARN of the AWS Key Management Service (AWS KMS) customer master key (CMK) that was used to protect the volume encryption key for the volume.

  

  



.. _Amazon EBS Volume Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html
.. _Creating or Restoring an Amazon EBS Volume: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-creating-volume.html
.. _Amazon EBS Encryption: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html
