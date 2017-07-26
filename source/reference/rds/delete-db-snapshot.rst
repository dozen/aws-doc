[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds delete-db-snapshot:


******************
delete-db-snapshot
******************



===========
Description
===========



Deletes a DBSnapshot. If the snapshot is being copied, the copy operation is terminated. 

 

.. note::

  The DBSnapshot must be in the ``available`` state to be deleted.



========
Synopsis
========

::

    delete-db-snapshot
  --db-snapshot-identifier <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-snapshot-identifier`` (string)


  The DBSnapshot identifier. 

   

  Constraints: Must be the name of an existing DB snapshot in the ``available`` state.

  

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

    

    

  

