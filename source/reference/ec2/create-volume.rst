[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-volume:


*************
create-volume
*************



===========
Description
===========



Creates an EBS volume that can be attached to an instance in the same Availability Zone. The volume is created in the regional endpoint that you send the HTTP request to. For more information see `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html>`_ .

 

You can create a new empty volume or restore a volume from an EBS snapshot. Any AWS Marketplace product codes from the snapshot are propagated to the volume.

 

You can create encrypted volumes with the ``Encrypted`` parameter. Encrypted volumes may only be attached to instances that support Amazon EBS encryption. Volumes that are created from encrypted snapshots are also automatically encrypted. For more information, see `Amazon EBS Encryption <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

You can tag your volumes during creation. For more information, see `Tagging Your Amazon EC2 Resources <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html>`_ .

 

For more information, see `Creating an Amazon EBS Volume <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-creating-volume.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateVolume>`_


========
Synopsis
========

::

    create-volume
  --availability-zone <value>
  [--encrypted | --no-encrypted]
  [--iops <value>]
  [--kms-key-id <value>]
  [--size <value>]
  [--snapshot-id <value>]
  [--volume-type <value>]
  [--dry-run | --no-dry-run]
  [--tag-specifications <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--availability-zone`` (string)


  The Availability Zone in which to create the volume. Use  describe-availability-zones to list the Availability Zones that are currently available to you.

  

``--encrypted`` | ``--no-encrypted`` (boolean)


  Specifies whether the volume should be encrypted. Encrypted Amazon EBS volumes may only be attached to instances that support Amazon EBS encryption. Volumes that are created from encrypted snapshots are automatically encrypted. There is no way to create an encrypted volume from an unencrypted snapshot or vice versa. If your AMI uses encrypted volumes, you can only launch it on supported instance types. For more information, see `Amazon EBS Encryption <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--iops`` (integer)


  Only valid for Provisioned IOPS SSD volumes. The number of I/O operations per second (IOPS) to provision for the volume, with a maximum ratio of 50 IOPS/GiB.

   

  Constraint: Range is 100 to 20000 for Provisioned IOPS SSD volumes 

  

``--kms-key-id`` (string)


  The full ARN of the AWS Key Management Service (AWS KMS) customer master key (CMK) to use when creating the encrypted volume. This parameter is only required if you want to use a non-default CMK; if this parameter is not specified, the default CMK for EBS is used. The ARN contains the ``arn:aws:kms`` namespace, followed by the region of the CMK, the AWS account ID of the CMK owner, the ``key`` namespace, and then the CMK ID. For example, arn:aws:kms:*us-east-1* :*012345678910* :key/*abcd1234-a123-456a-a12b-a123b4cd56ef* . If a ``KmsKeyId`` is specified, the ``Encrypted`` flag must also be set.

  

``--size`` (integer)


  The size of the volume, in GiBs.

   

  Constraints: 1-16384 for ``gp2`` , 4-16384 for ``io1`` , 500-16384 for ``st1`` , 500-16384 for ``sc1`` , and 1-1024 for ``standard`` . If you specify a snapshot, the volume size must be equal to or larger than the snapshot size.

   

  Default: If you're creating the volume from a snapshot and don't specify a volume size, the default is the snapshot size.

  

``--snapshot-id`` (string)


  The snapshot from which to create the volume.

  

``--volume-type`` (string)


  The volume type. This can be ``gp2`` for General Purpose SSD, ``io1`` for Provisioned IOPS SSD, ``st1`` for Throughput Optimized HDD, ``sc1`` for Cold HDD, or ``standard`` for Magnetic volumes.

   

  Default: ``standard``  

  

  Possible values:

  
  *   ``standard``

  
  *   ``io1``

  
  *   ``gp2``

  
  *   ``sc1``

  
  *   ``st1``

  

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--tag-specifications`` (list)


  The tags to apply to the volume during creation.

  



Shorthand Syntax::

    ResourceType=string,Tags=[{Key=string,Value=string},{Key=string,Value=string}] ...




JSON Syntax::

  [
    {
      "ResourceType": "customer-gateway"|"dhcp-options"|"image"|"instance"|"internet-gateway"|"network-acl"|"network-interface"|"reserved-instances"|"route-table"|"snapshot"|"spot-instances-request"|"subnet"|"security-group"|"volume"|"vpc"|"vpn-connection"|"vpn-gateway",
      "Tags": [
        {
          "Key": "string",
          "Value": "string"
        }
        ...
      ]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
       "VolumeId": "vol-1234567890abcdef0",
       "State": "creating",
       "SnapshotId": null,
       "CreateTime": "YYYY-MM-DDTHH:MM:SS.000Z",
       "Size": 80
   }

**To create a new Provisioned IOPS (SSD) volume from a snapshot**

This example command creates a new Provisioned IOPS (SSD) volume with 1000 provisioned IOPS from a snapshot in the Availability Zone ``us-east-1a``.

Command::

  aws ec2 create-volume --region us-east-1 --availability-zone us-east-1a --snapshot-id snap-066877671789bd71b --volume-type io1 --iops 1000

Output::

   {
       "AvailabilityZone": "us-east-1a",
       "Attachments": [],
       "Tags": [],
       "VolumeType": "io1",
       "VolumeId": "vol-1234567890abcdef0",
       "State": "creating",
       "Iops": 1000,
       "SnapshotId": "snap-066877671789bd71b",
       "CreateTime": "YYYY-MM-DDTHH:MM:SS.000Z",
       "Size": 500
   }

**To create a volume with tags**

This example creates a volume and applies two tags: ``purpose`` = ``production``, and ``cost-center`` = ``cc123``.

Command::

  aws ec2 create-volume --availability-zone us-east-1a --volume-type gp2 --size 80 --tag-specifications 'ResourceType=volume,Tags=[{Key=purpose,Value=production},{Key=cost-center,Value=cc123}]'

======
Output
======

Attachments -> (list)

  

  Information about the volume attachments.

  

  (structure)

    

    Describes volume attachment details.

    

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

      

      

    

  

AvailabilityZone -> (string)

  

  The Availability Zone for the volume.

  

  

CreateTime -> (timestamp)

  

  The time stamp when volume creation was initiated.

  

  

Encrypted -> (boolean)

  

  Indicates whether the volume will be encrypted.

  

  

KmsKeyId -> (string)

  

  The full ARN of the AWS Key Management Service (AWS KMS) customer master key (CMK) that was used to protect the volume encryption key for the volume.

  

  

Size -> (integer)

  

  The size of the volume, in GiBs.

  

  

SnapshotId -> (string)

  

  The snapshot from which the volume was created, if applicable.

  

  

State -> (string)

  

  The volume state.

  

  

VolumeId -> (string)

  

  The ID of the volume.

  

  

Iops -> (integer)

  

  The number of I/O operations per second (IOPS) that the volume supports. For Provisioned IOPS SSD volumes, this represents the number of IOPS that are provisioned for the volume. For General Purpose SSD volumes, this represents the baseline performance of the volume and the rate at which the volume accumulates I/O credits for bursting. For more information on General Purpose SSD baseline performance, I/O credits, and bursting, see `Amazon EBS Volume Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

   

  Constraint: Range is 100-20000 IOPS for io1 volumes and 100-10000 IOPS for ``gp2`` volumes.

   

  Condition: This parameter is required for requests to create ``io1`` volumes; it is not used in requests to create ``gp2`` , ``st1`` , ``sc1`` , or ``standard`` volumes.

  

  

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

  

  The volume type. This can be ``gp2`` for General Purpose SSD, ``io1`` for Provisioned IOPS SSD, ``st1`` for Throughput Optimized HDD, ``sc1`` for Cold HDD, or ``standard`` for Magnetic volumes.

  

  

