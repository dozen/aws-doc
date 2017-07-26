[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-snapshot:


***************
create-snapshot
***************



===========
Description
===========



Creates a snapshot of an EBS volume and stores it in Amazon S3. You can use snapshots for backups, to make copies of EBS volumes, and to save data before shutting down an instance.

 

When a snapshot is created, any AWS Marketplace product codes that are associated with the source volume are propagated to the snapshot.

 

You can take a snapshot of an attached volume that is in use. However, snapshots only capture data that has been written to your EBS volume at the time the snapshot command is issued; this may exclude any data that has been cached by any applications or the operating system. If you can pause any file systems on the volume long enough to take a snapshot, your snapshot should be complete. However, if you cannot pause all file writes to the volume, you should unmount the volume from within the instance, issue the snapshot command, and then remount the volume to ensure a consistent and complete snapshot. You may remount and use your volume while the snapshot status is ``pending`` .

 

To create a snapshot for EBS volumes that serve as root devices, you should stop the instance before taking the snapshot.

 

Snapshots that are taken from encrypted volumes are automatically encrypted. Volumes that are created from encrypted snapshots are also automatically encrypted. Your encrypted volumes and any associated snapshots always remain protected.

 

For more information, see `Amazon Elastic Block Store`_ and `Amazon EBS Encryption`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    create-snapshot
  [--dry-run | --no-dry-run]
  --volume-id <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--volume-id`` (string)


  The ID of the EBS volume.

  

``--description`` (string)


  A description for the snapshot.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a snapshot**

This example command creates a snapshot of the volume with a volume ID of ``vol-1234abcd`` and a short description to identify the snapshot.

Command::

  aws ec2 create-snapshot --volume-id vol-1234abcd --description "This is my root volume snapshot."

Output::

   {
       "Description": "This is my root volume snapshot.",
       "Tags": [],
       "VolumeId": "vol-1234abcd",
       "State": "pending",
       "VolumeSize": 8,
       "StartTime": "2014-02-28T21:06:01.000Z",
       "OwnerId": "012345678910",
       "SnapshotId": "snap-1a2b3c4d"
   }

======
Output
======

SnapshotId -> (string)

  

  The ID of the snapshot. Each snapshot receives a unique identifier when it is created.

  

  

VolumeId -> (string)

  

  The ID of the volume that was used to create the snapshot.

  

  

State -> (string)

  

  The snapshot state.

  

  

StateMessage -> (string)

  

  Encrypted Amazon EBS snapshots are copied asynchronously. If a snapshot copy operation fails (for example, if the proper AWS Key Management Service (AWS KMS) permissions are not obtained) this field displays error state details to help you diagnose why the error occurred. This parameter is only returned by the  describe-snapshots API operation.

  

  

StartTime -> (timestamp)

  

  The time stamp when the snapshot was initiated.

  

  

Progress -> (string)

  

  The progress of the snapshot, as a percentage.

  

  

OwnerId -> (string)

  

  The AWS account ID of the EBS snapshot owner.

  

  

Description -> (string)

  

  The description for the snapshot.

  

  

VolumeSize -> (integer)

  

  The size of the volume, in GiB.

  

  

OwnerAlias -> (string)

  

  The AWS account alias (for example, ``amazon`` , ``self`` ) or AWS account ID that owns the snapshot.

  

  

Tags -> (list)

  

  Any tags assigned to the snapshot.

  

  (structure)

    

    Describes a tag.

    

    Key -> (string)

      

      The key of the tag. 

       

      Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

      

      

    Value -> (string)

      

      The value of the tag.

       

      Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

      

      

    

  

Encrypted -> (boolean)

  

  Indicates whether the snapshot is encrypted.

  

  

KmsKeyId -> (string)

  

  The full ARN of the AWS Key Management Service (AWS KMS) customer master key (CMK) that was used to protect the volume encryption key for the parent volume.

  

  

DataEncryptionKeyId -> (string)

  

  The data encryption key identifier for the snapshot. This value is a unique identifier that corresponds to the data encryption key that was used to encrypt the original volume or snapshot copy. Because data encryption keys are inherited by volumes created from snapshots, and vice versa, if snapshots share the same data encryption key identifier, then they belong to the same volume/snapshot lineage. This parameter is only returned by the  describe-snapshots API operation.

  

  



.. _Amazon EBS Encryption: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html
.. _Amazon Elastic Block Store: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEBS.html
