[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds copy-db-snapshot:


****************
copy-db-snapshot
****************



===========
Description
===========



Copies the specified DB Snapshot. The source DB snapshot must be in the "available" state. 

 

If you are copying from a shared manual DB snapshot, the ``SourceDBSnapshotIdentifier`` must be the ARN of the shared DB snapshot.



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
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--source-db-snapshot-identifier`` (string)


  The identifier for the source DB snapshot. 

   

  If you are copying from a shared manual DB snapshot, this must be the ARN of the shared DB snapshot.

   

  Constraints:

   

   
  * Must specify a valid system snapshot in the "available" state.
   
  * If the source snapshot is in the same region as the copy, specify a valid DB snapshot identifier.
   
  * If the source snapshot is in a different region than the copy, specify a valid DB snapshot ARN. For more information, go to `Copying a DB Snapshot`_ .
   

   

  Example: ``rds:mydb-2012-04-02-00-01`` 

   

  Example: ``arn:aws:rds:rr-regn-1:123456789012:snapshot:mysql-instance1-snapshot-20130805`` 

  

``--target-db-snapshot-identifier`` (string)


  The identifier for the copied snapshot. 

   

  Constraints:

   

   
  * Cannot be null, empty, or blank
   
  * Must contain from 1 to 255 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

   

  Example: ``my-db-snapshot`` 

  

``--kms-key-id`` (string)


  The AWS Key Management Service (AWS KMS) key identifier for an encrypted DB snapshot. The KMS key identifier is the Amazon Resource Name (ARN) or the KMS key alias for the KMS encryption key. 

   

  If you copy an unencrypted DB snapshot and specify a value for the ``KmsKeyId`` parameter, Amazon RDS encrypts the target DB snapshot using the specified KMS encryption key.

   

  If you copy an encrypted DB snapshot from your AWS account, you can specify a value for ``KmsKeyId`` to encrypt the copy with a new KMS encryption key. If you don't specify a value for ``KmsKeyId`` then the copy of the DB snapshot is encrypted with the same KMS key as the source DB snapshot. 

   

  If you copy an encrypted DB snapshot that is shared from another AWS account, then you must specify a value for ``KmsKeyId`` .

  

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

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    Specifies the storage type associated with DB Snapshot. 

    

    

  TdeCredentialArn -> (string)

    

    The ARN from the Key Store with which to associate the instance for TDE encryption. 

    

    

  Encrypted -> (boolean)

    

    Specifies whether the DB snapshot is encrypted. 

    

    

  KmsKeyId -> (string)

    

    If ``Encrypted`` is true, the KMS key identifier for the encrypted DB snapshot. 

    

    

  



.. _Copying a DB Snapshot: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CopySnapshot.html
