[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds restore-db-cluster-from-snapshot:


********************************
restore-db-cluster-from-snapshot
********************************



===========
Description
===========



Creates a new DB cluster from a DB cluster snapshot. The target DB cluster is created from the source DB cluster restore point with the same configuration as the original source DB cluster, except that the new DB cluster is created with the default security group. 

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    restore-db-cluster-from-snapshot
  [--availability-zones <value>]
  --db-cluster-identifier <value>
  --snapshot-identifier <value>
  --engine <value>
  [--engine-version <value>]
  [--port <value>]
  [--db-subnet-group-name <value>]
  [--database-name <value>]
  [--option-group-name <value>]
  [--vpc-security-group-ids <value>]
  [--tags <value>]
  [--kms-key-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--availability-zones`` (list)


  Provides the list of EC2 Availability Zones that instances in the restored DB cluster can be created in.

  



Syntax::

  "string" "string" ...



``--db-cluster-identifier`` (string)


  The name of the DB cluster to create from the DB cluster snapshot. This parameter isn't case-sensitive. 

   

  Constraints:

   

   
  * Must contain from 1 to 255 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

   

  Example: ``my-snapshot-id`` 

  

``--snapshot-identifier`` (string)


  The identifier for the DB cluster snapshot to restore from. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--engine`` (string)


  The database engine to use for the new DB cluster. 

   

  Default: The same as source

   

  Constraint: Must be compatible with the engine of the source

  

``--engine-version`` (string)


  The version of the database engine to use for the new DB cluster.

  

``--port`` (integer)


  The port number on which the new DB cluster accepts connections. 

   

  Constraints: Value must be ``1150-65535`` 

   

  Default: The same port as the original DB cluster.

  

``--db-subnet-group-name`` (string)


  The name of the DB subnet group to use for the new DB cluster. 

   

  Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

   

  Example: ``mySubnetgroup`` 

  

``--database-name`` (string)


  The database name for the restored DB cluster. 

  

``--option-group-name`` (string)


  The name of the option group to use for the restored DB cluster. 

  

``--vpc-security-group-ids`` (list)


  A list of VPC security groups that the new DB cluster will belong to. 

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  The tags to be assigned to the restored DB cluster. 

  



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



``--kms-key-id`` (string)


  The KMS key identifier to use when restoring an encrypted DB cluster from an encrypted DB cluster snapshot.

   

  The KMS key identifier is the Amazon Resource Name (ARN) for the KMS encryption key. If you are restoring a DB cluster with the same AWS account that owns the KMS encryption key used to encrypt the new DB cluster, then you can use the KMS key alias instead of the ARN for the KMS encryption key.

   

  If you do not specify a value for the ``KmsKeyId`` parameter, then the following will occur:

   

   
  * If the DB cluster snapshot is encrypted, then the restored DB cluster is encrypted using the KMS key that was used to encrypt the DB cluster snapshot.
   
  * If the DB cluster snapshot is not encrypted, then the restored DB cluster is not encrypted.
   

   

  If ``SnapshotIdentifier`` refers to a DB cluster snapshot that is not encrypted, and you specify a value for the ``KmsKeyId`` parameter, then the restore request is rejected.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DBCluster -> (structure)

  

  Contains the result of a successful invocation of the following actions: 

   

   
  *  create-db-cluster  
   
  *  delete-db-cluster  
   
  *  failover-db-cluster  
   
  *  modify-db-cluster  
   
  *  restore-db-cluster-from-snapshot  
   

   

  This data type is used as a response element in the  describe-db-clusters action.

  

  AllocatedStorage -> (integer)

    

    Specifies the allocated storage size in gigabytes (GB). 

    

    

  AvailabilityZones -> (list)

    

    Provides the list of EC2 Availability Zones that instances in the DB cluster can be created in.

    

    (string)

      

      

    

  BackupRetentionPeriod -> (integer)

    

    Specifies the number of days for which automatic DB snapshots are retained. 

    

    

  CharacterSetName -> (string)

    

    If present, specifies the name of the character set that this cluster is associated with. 

    

    

  DatabaseName -> (string)

    

    Contains the name of the initial database of this DB cluster that was provided at create time, if one was specified when the DB cluster was created. This same name is returned for the life of the DB cluster. 

    

    

  DBClusterIdentifier -> (string)

    

    Contains a user-supplied DB cluster identifier. This identifier is the unique key that identifies a DB cluster. 

    

    

  DBClusterParameterGroup -> (string)

    

    Specifies the name of the DB cluster parameter group for the DB cluster.

    

    

  DBSubnetGroup -> (string)

    

    Specifies information on the subnet group associated with the DB cluster, including the name, description, and subnets in the subnet group. 

    

    

  Status -> (string)

    

    Specifies the current state of this DB cluster. 

    

    

  PercentProgress -> (string)

    

    Specifies the progress of the operation as a percentage. 

    

    

  EarliestRestorableTime -> (timestamp)

    

    Specifies the earliest time to which a database can be restored with point-in-time restore. 

    

    

  Endpoint -> (string)

    

    Specifies the connection endpoint for the primary instance of the DB cluster. 

    

    

  Engine -> (string)

    

    Provides the name of the database engine to be used for this DB cluster. 

    

    

  EngineVersion -> (string)

    

    Indicates the database engine version. 

    

    

  LatestRestorableTime -> (timestamp)

    

    Specifies the latest time to which a database can be restored with point-in-time restore. 

    

    

  Port -> (integer)

    

    Specifies the port that the database engine is listening on. 

    

    

  MasterUsername -> (string)

    

    Contains the master username for the DB cluster. 

    

    

  DBClusterOptionGroupMemberships -> (list)

    

    Provides the list of option group memberships for this DB cluster. 

    

    (structure)

      

      Contains status information for a DB cluster option group.

      

      DBClusterOptionGroupName -> (string)

        

        Specifies the name of the DB cluster option group.

        

        

      Status -> (string)

        

        Specifies the status of the DB cluster option group.

        

        

      

    

  PreferredBackupWindow -> (string)

    

    Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

    

    

  PreferredMaintenanceWindow -> (string)

    

    Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC). 

    

    

  DBClusterMembers -> (list)

    

    Provides the list of instances that make up the DB cluster.

    

    (structure)

      

      Contains information about an instance that is part of a DB cluster.

      

      DBInstanceIdentifier -> (string)

        

        Specifies the instance identifier for this member of the DB cluster.

        

        

      IsClusterWriter -> (boolean)

        

        Value that is ``true`` if the cluster member is the primary instance for the DB cluster and ``false`` otherwise.

        

        

      DBClusterParameterGroupStatus -> (string)

        

        Specifies the status of the DB cluster parameter group for this member of the DB cluster. 

        

        

      

    

  VpcSecurityGroups -> (list)

    

    Provides a list of VPC security groups that the DB cluster belongs to. 

    

    (structure)

      

      This data type is used as a response element for queries on VPC security group membership.

      

      VpcSecurityGroupId -> (string)

        

        The name of the VPC security group.

        

        

      Status -> (string)

        

        The status of the VPC security group. 

        

        

      

    

  HostedZoneId -> (string)

    

    Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

    

    

  StorageEncrypted -> (boolean)

    

    Specifies whether the DB cluster is encrypted.

    

    

  KmsKeyId -> (string)

    

    If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB cluster.

    

    

  DbClusterResourceId -> (string)

    

    The region-unique, immutable identifier for the DB cluster. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB cluster is accessed. 

    

    

  



.. _Aurora on Amazon RDS: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html
