[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds copy-db-cluster-snapshot:


************************
copy-db-cluster-snapshot
************************



===========
Description
===========



Copies a snapshot of a DB cluster.

 

To copy a DB cluster snapshot from a shared manual DB cluster snapshot, ``SourceDBClusterSnapshotIdentifier`` must be the Amazon Resource Name (ARN) of the shared DB cluster snapshot.

 

You can copy an encrypted DB cluster snapshot from another AWS region. In that case, the region where you call the ``copy-db-cluster-snapshot`` action is the destination region for the encrypted DB cluster snapshot to be copied to. To copy an encrypted DB cluster snapshot from another region, you must provide the following values:

 

 
* ``KmsKeyId`` - The AWS Key Management System (KMS) key identifier for the key to use to encrypt the copy of the DB cluster snapshot in the destination region. 
 
* ``PreSignedUrl`` - A URL that contains a Signature Version 4 signed request for the ``copy-db-cluster-snapshot`` action to be called in the source region where the DB cluster snapshot will be copied from. The pre-signed URL must be a valid request for the ``copy-db-cluster-snapshot`` API action that can be executed in the source region that contains the encrypted DB cluster snapshot to be copied. The pre-signed URL request must contain the following parameter values: 

   
  * ``KmsKeyId`` - The KMS key identifier for the key to use to encrypt the copy of the DB cluster snapshot in the destination region. This is the same identifier for both the ``copy-db-cluster-snapshot`` action that is called in the destination region, and the action contained in the pre-signed URL. 
   
  * ``DestinationRegion`` - The name of the region that the DB cluster snapshot will be created in. 
   
  * ``SourceDBClusterSnapshotIdentifier`` - The DB cluster snapshot identifier for the encrypted DB cluster snapshot to be copied. This identifier must be in the Amazon Resource Name (ARN) format for the source region. For example, if you are copying an encrypted DB cluster snapshot from the us-west-2 region, then your ``SourceDBClusterSnapshotIdentifier`` looks like the following example: ``arn:aws:rds:us-west-2:123456789012:cluster-snapshot:aurora-cluster1-snapshot-20161115`` . 
   

 

To learn how to generate a Signature Version 4 signed request, see `Authenticating Requests\: Using Query Parameters (AWS Signature Version 4) <http://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-query-string-auth.html>`_ and `Signature Version 4 Signing Process <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

 
 
* ``TargetDBClusterSnapshotIdentifier`` - The identifier for the new copy of the DB cluster snapshot in the destination region. 
 
* ``SourceDBClusterSnapshotIdentifier`` - The DB cluster snapshot identifier for the encrypted DB cluster snapshot to be copied. This identifier must be in the ARN format for the source region and is the same value as the ``SourceDBClusterSnapshotIdentifier`` in the pre-signed URL.  
 

 

To cancel the copy operation once it is in progress, delete the target DB cluster snapshot identified by ``TargetDBClusterSnapshotIdentifier`` while that DB cluster snapshot is in "copying" status.

 

For more information on copying encrypted DB cluster snapshots from one region to another, see `Copying a DB Cluster Snapshot in the Same Account, Either in the Same Region or Across Regions <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CopySnapshot.html#USER_CopyDBClusterSnapshot.CrossRegion>`_ in the Amazon RDS User Guide.

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html>`_ in the *Amazon RDS User Guide.*  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/CopyDBClusterSnapshot>`_


========
Synopsis
========

::

    copy-db-cluster-snapshot
  --source-db-cluster-snapshot-identifier <value>
  --target-db-cluster-snapshot-identifier <value>
  [--kms-key-id <value>]
  [--pre-signed-url <value>]
  [--copy-tags | --no-copy-tags]
  [--tags <value>]
  [--source-region <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-db-cluster-snapshot-identifier`` (string)


  The identifier of the DB cluster snapshot to copy. This parameter is not case-sensitive.

   

  You cannot copy an encrypted, shared DB cluster snapshot from one AWS region to another.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens. 
   
  * First character must be a letter. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   
  * Must specify a valid system snapshot in the "available" state. 
   
  * If the source snapshot is in the same region as the copy, specify a valid DB snapshot identifier. 
   
  * If the source snapshot is in a different region than the copy, specify a valid DB cluster snapshot ARN. For more information, go to `Copying a DB Snapshot or DB Cluster Snapshot <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CopySnapshot.html>`_ . 
   

   

  Example: ``my-cluster-snapshot1``  

  

``--target-db-cluster-snapshot-identifier`` (string)


  The identifier of the new DB cluster snapshot to create from the source DB cluster snapshot. This parameter is not case-sensitive.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens. 
   
  * First character must be a letter. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   

   

  Example: ``my-cluster-snapshot2``  

  

``--kms-key-id`` (string)


  The AWS KMS key ID for an encrypted DB cluster snapshot. The KMS key ID is the Amazon Resource Name (ARN), KMS key identifier, or the KMS key alias for the KMS encryption key. 

   

  If you copy an unencrypted DB cluster snapshot and specify a value for the ``KmsKeyId`` parameter, Amazon RDS encrypts the target DB cluster snapshot using the specified KMS encryption key. 

   

  If you copy an encrypted DB cluster snapshot from your AWS account, you can specify a value for ``KmsKeyId`` to encrypt the copy with a new KMS encryption key. If you don't specify a value for ``KmsKeyId`` , then the copy of the DB cluster snapshot is encrypted with the same KMS key as the source DB cluster snapshot. 

   

  If you copy an encrypted DB cluster snapshot that is shared from another AWS account, then you must specify a value for ``KmsKeyId`` . 

   

  To copy an encrypted DB cluster snapshot to another region, you must set ``KmsKeyId`` to the KMS key ID you want to use to encrypt the copy of the DB cluster snapshot in the destination region. KMS encryption keys are specific to the region that they are created in, and you cannot use encryption keys from one region in another region.

  

``--pre-signed-url`` (string)


  The URL that contains a Signature Version 4 signed request for the ``copy-db-cluster-snapshot`` API action in the AWS region that contains the source DB cluster snapshot to copy. The ``PreSignedUrl`` parameter must be used when copying an encrypted DB cluster snapshot from another AWS region.

   

  The pre-signed URL must be a valid request for the ``CopyDBSClusterSnapshot`` API action that can be executed in the source region that contains the encrypted DB cluster snapshot to be copied. The pre-signed URL request must contain the following parameter values:

   

   
  * ``KmsKeyId`` - The KMS key identifier for the key to use to encrypt the copy of the DB cluster snapshot in the destination region. This is the same identifier for both the ``copy-db-cluster-snapshot`` action that is called in the destination region, and the action contained in the pre-signed URL. 
   
  * ``DestinationRegion`` - The name of the region that the DB cluster snapshot will be created in. 
   
  * ``SourceDBClusterSnapshotIdentifier`` - The DB cluster snapshot identifier for the encrypted DB cluster snapshot to be copied. This identifier must be in the Amazon Resource Name (ARN) format for the source region. For example, if you are copying an encrypted DB cluster snapshot from the us-west-2 region, then your ``SourceDBClusterSnapshotIdentifier`` looks like the following example: ``arn:aws:rds:us-west-2:123456789012:cluster-snapshot:aurora-cluster1-snapshot-20161115`` . 
   

   

  To learn how to generate a Signature Version 4 signed request, see `Authenticating Requests\: Using Query Parameters (AWS Signature Version 4) <http://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-query-string-auth.html>`_ and `Signature Version 4 Signing Process <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

  

``--copy-tags`` | ``--no-copy-tags`` (boolean)


  True to copy all tags from the source DB cluster snapshot to the target DB cluster snapshot; otherwise false. The default is false.

  

``--tags`` (list)


  A list of tags.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--source-region`` (string)


  The ID of the region that contains the snapshot to be copied.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DBClusterSnapshot -> (structure)

  

  Contains the result of a successful invocation of the following actions:

   

   
  *  create-db-cluster-snapshot   
   
  *  delete-db-cluster-snapshot   
   

   

  This data type is used as a response element in the  describe-db-cluster-snapshots action.

  

  AvailabilityZones -> (list)

    

    Provides the list of EC2 Availability Zones that instances in the DB cluster snapshot can be restored in.

    

    (string)

      

      

    

  DBClusterSnapshotIdentifier -> (string)

    

    Specifies the identifier for the DB cluster snapshot.

    

    

  DBClusterIdentifier -> (string)

    

    Specifies the DB cluster identifier of the DB cluster that this DB cluster snapshot was created from.

    

    

  SnapshotCreateTime -> (timestamp)

    

    Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

    

    

  Engine -> (string)

    

    Specifies the name of the database engine.

    

    

  AllocatedStorage -> (integer)

    

    Specifies the allocated storage size in gigabytes (GB).

    

    

  Status -> (string)

    

    Specifies the status of this DB cluster snapshot.

    

    

  Port -> (integer)

    

    Specifies the port that the DB cluster was listening on at the time of the snapshot.

    

    

  VpcId -> (string)

    

    Provides the VPC ID associated with the DB cluster snapshot.

    

    

  ClusterCreateTime -> (timestamp)

    

    Specifies the time when the DB cluster was created, in Universal Coordinated Time (UTC).

    

    

  MasterUsername -> (string)

    

    Provides the master username for the DB cluster snapshot.

    

    

  EngineVersion -> (string)

    

    Provides the version of the database engine for this DB cluster snapshot.

    

    

  LicenseModel -> (string)

    

    Provides the license model information for this DB cluster snapshot.

    

    

  SnapshotType -> (string)

    

    Provides the type of the DB cluster snapshot.

    

    

  PercentProgress -> (integer)

    

    Specifies the percentage of the estimated data that has been transferred.

    

    

  StorageEncrypted -> (boolean)

    

    Specifies whether the DB cluster snapshot is encrypted.

    

    

  KmsKeyId -> (string)

    

    If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster snapshot.

    

    

  DBClusterSnapshotArn -> (string)

    

    The Amazon Resource Name (ARN) for the DB cluster snapshot.

    

    

  SourceDBClusterSnapshotArn -> (string)

    

    If the DB cluster snapshot was copied from a source DB cluster snapshot, the Amazon Resource Name (ARN) for the source DB cluster snapshot; otherwise, a null value.

    

    

  IAMDatabaseAuthenticationEnabled -> (boolean)

    

    True if mapping of AWS Identity and Access Management (IAM) accounts to database accounts is enabled; otherwise false.

    

    

  

