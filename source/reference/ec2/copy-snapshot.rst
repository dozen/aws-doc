[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 copy-snapshot:


*************
copy-snapshot
*************



===========
Description
===========



Copies a point-in-time snapshot of an EBS volume and stores it in Amazon S3. You can copy the snapshot within the same region or from one region to another. You can use the snapshot to create EBS volumes or Amazon Machine Images (AMIs). The snapshot is copied to the regional endpoint that you send the HTTP request to.

 

Copies of encrypted EBS snapshots remain encrypted. Copies of unencrypted snapshots remain unencrypted, unless the ``Encrypted`` flag is specified during the snapshot copy operation. By default, encrypted snapshot copies use the default AWS Key Management Service (AWS KMS) customer master key (CMK); however, you can specify a non-default CMK with the ``KmsKeyId`` parameter.

 

For more information, see `Copying an Amazon EBS Snapshot`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    copy-snapshot
  [--dry-run | --no-dry-run]
  --source-region <value>
  --source-snapshot-id <value>
  [--description <value>]
  [--destination-region <value>]
  [--presigned-url <value>]
  [--encrypted | --no-encrypted]
  [--kms-key-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--source-region`` (string)


  The ID of the region that contains the snapshot to be copied.

  

``--source-snapshot-id`` (string)


  The ID of the EBS snapshot to copy.

  

``--description`` (string)


  A description for the EBS snapshot.

  

``--destination-region`` (string)


  The destination region to use in the ``PresignedUrl`` parameter of a snapshot copy operation. This parameter is only valid for specifying the destination region in a ``PresignedUrl`` parameter, where it is required.

   

  .. note::

     

    ``copy-snapshot`` sends the snapshot copy to the regional endpoint that you send the HTTP request to, such as ``ec2.us-east-1.amazonaws.com`` (in the AWS CLI, this is specified with the ``--region`` parameter or the default region in your AWS configuration file).

     

  

``--presigned-url`` (string)


  The pre-signed URL that facilitates copying an encrypted snapshot. This parameter is only required when copying an encrypted snapshot with the Amazon EC2 Query API; it is available as an optional parameter in all other cases. The ``PresignedUrl`` should use the snapshot source endpoint, the ``copy-snapshot`` action, and include the ``SourceRegion`` , ``SourceSnapshotId`` , and ``DestinationRegion`` parameters. The ``PresignedUrl`` must be signed using AWS Signature Version 4. Because EBS snapshots are stored in Amazon S3, the signing algorithm for this parameter uses the same logic that is described in `Authenticating Requests by Using Query Parameters (AWS Signature Version 4)`_ in the *Amazon Simple Storage Service API Reference* . An invalid or improperly signed ``PresignedUrl`` will cause the copy operation to fail asynchronously, and the snapshot will move to an ``error`` state.

  

``--encrypted`` | ``--no-encrypted`` (boolean)


  Specifies whether the destination snapshot should be encrypted. There is no way to create an unencrypted snapshot copy from an encrypted snapshot; however, you can encrypt a copy of an unencrypted snapshot with this flag. The default CMK for EBS is used unless a non-default AWS Key Management Service (AWS KMS) CMK is specified with ``KmsKeyId`` . For more information, see `Amazon EBS Encryption`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--kms-key-id`` (string)


  The full ARN of the AWS Key Management Service (AWS KMS) CMK to use when creating the snapshot copy. This parameter is only required if you want to use a non-default CMK; if this parameter is not specified, the default CMK for EBS is used. The ARN contains the ``arn:aws:kms`` namespace, followed by the region of the CMK, the AWS account ID of the CMK owner, the ``key`` namespace, and then the CMK ID. For example, arn:aws:kms:*us-east-1* :*012345678910* :key/*abcd1234-a123-456a-a12b-a123b4cd56ef* . The specified CMK must exist in the region that the snapshot is being copied to. If a ``KmsKeyId`` is specified, the ``Encrypted`` flag must also be set.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To copy a snapshot**

This example command copies a snapshot with the snapshot ID of ``snap-1234abcd`` from the ``us-west-2`` region to the ``us-east-1`` region and adds a short description to identify the snapshot.

Command::

  aws --region us-east-1 ec2 copy-snapshot --source-region us-west-2 --source-snapshot-id snap-1234abcd --description "This is my copied snapshot."

Output::

   {
       "SnapshotId": "snap-2345bcde"
   }

======
Output
======

SnapshotId -> (string)

  

  The ID of the new snapshot.

  

  



.. _Copying an Amazon EBS Snapshot: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-copy-snapshot.html
.. _Authenticating Requests by Using Query Parameters (AWS Signature Version 4): http://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-query-string-auth.html
.. _Amazon EBS Encryption: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html
