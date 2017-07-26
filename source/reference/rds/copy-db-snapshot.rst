[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds copy-db-snapshot:


****************
copy-db-snapshot
****************



===========
Description
===========



Copies the specified DB snapshot. The source DB snapshot must be in the "available" state.

 

You can copy a snapshot from one AWS region to another. In that case, the region where you call the ``copy-db-snapshot`` action is the destination region for the DB snapshot copy. 

 

You cannot copy an encrypted, shared DB snapshot from one AWS region to another.

 

For more information about copying snapshots, see `Copying a DB Snapshot <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CopyDBSnapshot.html>`_ in the Amazon RDS User Guide. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/CopyDBSnapshot>`_


========
Synopsis
========

::

    copy-db-snapshot
  --source-db-snapshot-identifier <value>
  --target-db-snapshot-identifier <value>
  [--kms-key-id <value>]
  [--tags <value>]
  [--copy-tags | --no-copy-tags]
  [--pre-signed-url <value>]
  [--option-group-name <value>]
  [--source-region <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-db-snapshot-identifier`` (string)


  The identifier for the source DB snapshot.

   

  If the source snapshot is in the same region as the copy, specify a valid DB snapshot identifier. For example, ``rds:mysql-instance1-snapshot-20130805`` . 

   

  If the source snapshot is in a different region than the copy, specify a valid DB snapshot ARN. For example, ``arn:aws:rds:us-west-2:123456789012:snapshot:mysql-instance1-snapshot-20130805`` . 

   

  If you are copying from a shared manual DB snapshot, this parameter must be the Amazon Resource Name (ARN) of the shared DB snapshot. 

   

  If you are copying an encrypted snapshot this parameter must be in the ARN format for the source region, and must match the ``SourceDBSnapshotIdentifier`` in the ``PreSignedUrl`` parameter. 

   

  Constraints:

   

   
  * Must specify a valid system snapshot in the "available" state. 
   

   

  Example: ``rds:mydb-2012-04-02-00-01``  

   

  Example: ``arn:aws:rds:us-west-2:123456789012:snapshot:mysql-instance1-snapshot-20130805``  

  

``--target-db-snapshot-identifier`` (string)


  The identifier for the copy of the snapshot. 

   

  Constraints:

   

   
  * Cannot be null, empty, or blank 
   
  * Must contain from 1 to 255 alphanumeric characters or hyphens 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

   

  Example: ``my-db-snapshot``  

  

``--kms-key-id`` (string)


  The AWS KMS key ID for an encrypted DB snapshot. The KMS key ID is the Amazon Resource Name (ARN), KMS key identifier, or the KMS key alias for the KMS encryption key. 

   

  If you copy an encrypted DB snapshot from your AWS account, you can specify a value for this parameter to encrypt the copy with a new KMS encryption key. If you don't specify a value for this parameter, then the copy of the DB snapshot is encrypted with the same KMS key as the source DB snapshot. 

   

  If you copy an encrypted DB snapshot that is shared from another AWS account, then you must specify a value for this parameter. 

   

  If you specify this parameter when you copy an unencrypted snapshot, the copy is encrypted. 

   

  If you copy an encrypted snapshot to a different AWS region, then you must specify a KMS key for the destination AWS region. KMS encryption keys are specific to the region that they are created in, and you cannot use encryption keys from one region in another region. 

  

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



``--copy-tags`` | ``--no-copy-tags`` (boolean)


  True to copy all tags from the source DB snapshot to the target DB snapshot; otherwise false. The default is false.

  

``--pre-signed-url`` (string)


  The URL that contains a Signature Version 4 signed request for the ``copy-db-snapshot`` API action in the source AWS region that contains the source DB snapshot to copy. 

   

  You must specify this parameter when you copy an encrypted DB snapshot from another AWS region by using the Amazon RDS API. You can specify the source region option instead of this parameter when you copy an encrypted DB snapshot from another AWS region by using the AWS CLI. 

   

  The presigned URL must be a valid request for the ``copy-db-snapshot`` API action that can be executed in the source region that contains the encrypted DB snapshot to be copied. The presigned URL request must contain the following parameter values: 

   

   
  * ``DestinationRegion`` - The AWS Region that the encrypted DB snapshot will be copied to. This region is the same one where the ``copy-db-snapshot`` action is called that contains this presigned URL.  For example, if you copy an encrypted DB snapshot from the us-west-2 region to the us-east-1 region, then you will call the ``copy-db-snapshot`` action in the us-east-1 region and provide a presigned URL that contains a call to the ``copy-db-snapshot`` action in the us-west-2 region. For this example, the ``DestinationRegion`` in the presigned URL must be set to the us-east-1 region.  
   
  * ``KmsKeyId`` - The KMS key identifier for the key to use to encrypt the copy of the DB snapshot in the destination region. This is the same identifier for both the ``copy-db-snapshot`` action that is called in the destination region, and the action contained in the presigned URL.  
   
  * ``SourceDBSnapshotIdentifier`` - The DB snapshot identifier for the encrypted snapshot to be copied. This identifier must be in the Amazon Resource Name (ARN) format for the source region. For example, if you are copying an encrypted DB snapshot from the us-west-2 region, then your ``SourceDBSnapshotIdentifier`` looks like the following example: ``arn:aws:rds:us-west-2:123456789012:snapshot:mysql-instance1-snapshot-20161115`` .  
   

   

  To learn how to generate a Signature Version 4 signed request, see `Authenticating Requests\: Using Query Parameters (AWS Signature Version 4) <http://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-query-string-auth.html>`_ and `Signature Version 4 Signing Process <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ . 

  

``--option-group-name`` (string)


  The name of an option group to associate with the copy. 

   

  Specify this option if you are copying a snapshot from one AWS region to another, and your DB instance uses a non-default option group. If your source DB instance uses Transparent Data Encryption for Oracle or Microsoft SQL Server, you must specify this option when copying across regions. For more information, see `Option Group Considerations <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CopySnapshot.html#USER_CopySnapshot.Options>`_ . 

  

``--source-region`` (string)


  The ID of the region that contains the snapshot to be copied.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DBSnapshot -> (structure)

  

  Contains the result of a successful invocation of the following actions:

   

   
  *  create-db-snapshot   
   
  *  delete-db-snapshot   
   

   

  This data type is used as a response element in the  describe-db-snapshots action.

  

  DBSnapshotIdentifier -> (string)

    

    Specifies the identifier for the DB snapshot.

    

    

  DBInstanceIdentifier -> (string)

    

    Specifies the DB instance identifier of the DB instance this DB snapshot was created from.

    

    

  SnapshotCreateTime -> (timestamp)

    

    Provides the time when the snapshot was taken, in Universal Coordinated Time (UTC).

    

    

  Engine -> (string)

    

    Specifies the name of the database engine.

    

    

  AllocatedStorage -> (integer)

    

    Specifies the allocated storage size in gigabytes (GB).

    

    

  Status -> (string)

    

    Specifies the status of this DB snapshot.

    

    

  Port -> (integer)

    

    Specifies the port that the database engine was listening on at the time of the snapshot.

    

    

  AvailabilityZone -> (string)

    

    Specifies the name of the Availability Zone the DB instance was located in at the time of the DB snapshot.

    

    

  VpcId -> (string)

    

    Provides the VPC ID associated with the DB snapshot.

    

    

  InstanceCreateTime -> (timestamp)

    

    Specifies the time when the snapshot was taken, in Universal Coordinated Time (UTC).

    

    

  MasterUsername -> (string)

    

    Provides the master username for the DB snapshot.

    

    

  EngineVersion -> (string)

    

    Specifies the version of the database engine.

    

    

  LicenseModel -> (string)

    

    License model information for the restored DB instance.

    

    

  SnapshotType -> (string)

    

    Provides the type of the DB snapshot.

    

    

  Iops -> (integer)

    

    Specifies the Provisioned IOPS (I/O operations per second) value of the DB instance at the time of the snapshot.

    

    

  OptionGroupName -> (string)

    

    Provides the option group name for the DB snapshot.

    

    

  PercentProgress -> (integer)

    

    The percentage of the estimated data that has been transferred.

    

    

  SourceRegion -> (string)

    

    The region that the DB snapshot was created in or copied from.

    

    

  SourceDBSnapshotIdentifier -> (string)

    

    The DB snapshot Arn that the DB snapshot was copied from. It only has value in case of cross customer or cross region copy.

    

    

  StorageType -> (string)

    

    Specifies the storage type associated with DB snapshot.

    

    

  TdeCredentialArn -> (string)

    

    The ARN from the key store with which to associate the instance for TDE encryption.

    

    

  Encrypted -> (boolean)

    

    Specifies whether the DB snapshot is encrypted.

    

    

  KmsKeyId -> (string)

    

    If ``Encrypted`` is true, the KMS key identifier for the encrypted DB snapshot. 

    

    

  DBSnapshotArn -> (string)

    

    The Amazon Resource Name (ARN) for the DB snapshot.

    

    

  Timezone -> (string)

    

    The time zone of the DB snapshot. In most cases, the ``Timezone`` element is empty. ``Timezone`` content appears only for snapshots taken from Microsoft SQL Server DB instances that were created with a time zone specified. 

    

    

  IAMDatabaseAuthenticationEnabled -> (boolean)

    

    True if mapping of AWS Identity and Access Management (IAM) accounts to database accounts is enabled; otherwise false.

    

    

  

