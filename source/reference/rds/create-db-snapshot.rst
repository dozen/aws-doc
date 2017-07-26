[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds create-db-snapshot:


******************
create-db-snapshot
******************



===========
Description
===========



Creates a DBSnapshot. The source DBInstance must be in "available" state.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/CreateDBSnapshot>`_


========
Synopsis
========

::

    create-db-snapshot
  --db-snapshot-identifier <value>
  --db-instance-identifier <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-snapshot-identifier`` (string)


  The identifier for the DB snapshot.

   

  Constraints:

   

   
  * Cannot be null, empty, or blank 
   
  * Must contain from 1 to 255 alphanumeric characters or hyphens 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

   

  Example: ``my-snapshot-id``  

  

``--db-instance-identifier`` (string)


  The DB instance identifier. This is the unique key that identifies a DB instance.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

  

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

    

    

  

