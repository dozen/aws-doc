[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds restore-db-cluster-to-point-in-time:


***********************************
restore-db-cluster-to-point-in-time
***********************************



===========
Description
===========



Restores a DB cluster to an arbitrary point in time. Users can restore to any point in time before ``LatestRestorableTime`` for up to ``BackupRetentionPeriod`` days. The target DB cluster is created from the source DB cluster with the same configuration as the original DB cluster, except that the new DB cluster is created with the default DB security group. 

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html>`_ in the *Amazon RDS User Guide.*  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/RestoreDBClusterToPointInTime>`_


========
Synopsis
========

::

    restore-db-cluster-to-point-in-time
  --db-cluster-identifier <value>
  [--restore-type <value>]
  --source-db-cluster-identifier <value>
  [--restore-to-time <value>]
  [--use-latest-restorable-time | --no-use-latest-restorable-time]
  [--port <value>]
  [--db-subnet-group-name <value>]
  [--option-group-name <value>]
  [--vpc-security-group-ids <value>]
  [--tags <value>]
  [--kms-key-id <value>]
  [--enable-iam-database-authentication | --no-enable-iam-database-authentication]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-cluster-identifier`` (string)


  The name of the new DB cluster to be created.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

  

``--restore-type`` (string)


  The type of restore to be performed. You can specify one of the following values:

   

   
  * ``full-copy`` - The new DB cluster is restored as a full copy of the source DB cluster. 
   
  * ``copy-on-write`` - The new DB cluster is restored as a clone of the source DB cluster. 
   

   

  Constraints: You cannot specify ``copy-on-write`` if the engine version of the source DB cluster is earlier than 1.11.

   

  If you don't specify a ``RestoreType`` value, then the new DB cluster is restored as a full copy of the source DB cluster.

  

``--source-db-cluster-identifier`` (string)


  The identifier of the source DB cluster from which to restore.

   

  Constraints:

   

   
  * Must be the identifier of an existing database instance 
   
  * Must contain from 1 to 63 alphanumeric characters or hyphens 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

  

``--restore-to-time`` (timestamp)


  The date and time to restore the DB cluster to.

   

  Valid Values: Value must be a time in Universal Coordinated Time (UTC) format

   

  Constraints:

   

   
  * Must be before the latest restorable time for the DB instance 
   
  * Must be specified if ``UseLatestRestorableTime`` parameter is not provided 
   
  * Cannot be specified if ``UseLatestRestorableTime`` parameter is true 
   
  * Cannot be specified if ``RestoreType`` parameter is ``copy-on-write``   
   

   

  Example: ``2015-03-07T23:45:00Z``  

  

``--use-latest-restorable-time`` | ``--no-use-latest-restorable-time`` (boolean)


  A value that is set to ``true`` to restore the DB cluster to the latest restorable backup time, and ``false`` otherwise. 

   

  Default: ``false``  

   

  Constraints: Cannot be specified if ``RestoreToTime`` parameter is provided.

  

``--port`` (integer)


  The port number on which the new DB cluster accepts connections.

   

  Constraints: Value must be ``1150-65535``  

   

  Default: The same port as the original DB cluster.

  

``--db-subnet-group-name`` (string)


  The DB subnet group name to use for the new DB cluster.

   

  Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

   

  Example: ``mySubnetgroup``  

  

``--option-group-name`` (string)


  The name of the option group for the new DB cluster.

  

``--vpc-security-group-ids`` (list)


  A list of VPC security groups that the new DB cluster belongs to.

  



Syntax::

  "string" "string" ...



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



``--kms-key-id`` (string)


  The KMS key identifier to use when restoring an encrypted DB cluster from an encrypted DB cluster.

   

  The KMS key identifier is the Amazon Resource Name (ARN) for the KMS encryption key. If you are restoring a DB cluster with the same AWS account that owns the KMS encryption key used to encrypt the new DB cluster, then you can use the KMS key alias instead of the ARN for the KMS encryption key.

   

  You can restore to a new DB cluster and encrypt the new DB cluster with a KMS key that is different than the KMS key used to encrypt the source DB cluster. The new DB cluster will be encrypted with the KMS key identified by the ``KmsKeyId`` parameter.

   

  If you do not specify a value for the ``KmsKeyId`` parameter, then the following will occur:

   

   
  * If the DB cluster is encrypted, then the restored DB cluster is encrypted using the KMS key that was used to encrypt the source DB cluster. 
   
  * If the DB cluster is not encrypted, then the restored DB cluster is not encrypted. 
   

   

  If ``DBClusterIdentifier`` refers to a DB cluster that is not encrypted, then the restore request is rejected.

  

``--enable-iam-database-authentication`` | ``--no-enable-iam-database-authentication`` (boolean)


  A use-latest-restorable-time value that is true to enable mapping of AWS Identity and Access Management (IAM) accounts to database accounts, and otherwise false.

   

  Default: ``false``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
   
  *  restore-db-cluster-to-point-in-time   
   

   

  This data type is used as a response element in the  describe-db-clusters action.

  

  AllocatedStorage -> (integer)

    

    For all database engines except Amazon Aurora, ``AllocatedStorage`` specifies the allocated storage size in gigabytes (GB). For Aurora, ``AllocatedStorage`` always returns 1, because Aurora DB cluster storage size is not fixed, but instead automatically adjusts as needed.

    

    

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

    

    

  ReaderEndpoint -> (string)

    

    The reader endpoint for the DB cluster. The reader endpoint for a DB cluster load-balances connections across the Aurora Replicas that are available in a DB cluster. As clients request new connections to the reader endpoint, Aurora distributes the connection requests among the Aurora Replicas in the DB cluster. This functionality can help balance your read workload across multiple Aurora Replicas in your DB cluster. 

     

    If a failover occurs, and the Aurora Replica that you are connected to is promoted to be the primary instance, your connection will be dropped. To continue sending your read workload to other Aurora Replicas in the cluster, you can then reconnect to the reader endpoint.

    

    

  MultiAZ -> (boolean)

    

    Specifies whether the DB cluster has instances in multiple Availability Zones.

    

    

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

    

    

  ReplicationSourceIdentifier -> (string)

    

    Contains the identifier of the source DB cluster if this DB cluster is a Read Replica.

    

    

  ReadReplicaIdentifiers -> (list)

    

    Contains one or more identifiers of the Read Replicas associated with this DB cluster.

    

    (string)

      

      

    

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

        

        

      PromotionTier -> (integer)

        

        A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Aurora.Managing.html#Aurora.Managing.FaultTolerance>`_ . 

        

        

      

    

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

    

    

  DBClusterArn -> (string)

    

    The Amazon Resource Name (ARN) for the DB cluster.

    

    

  AssociatedRoles -> (list)

    

    Provides a list of the AWS Identity and Access Management (IAM) roles that are associated with the DB cluster. IAM roles that are associated with a DB cluster grant permission for the DB cluster to access other AWS services on your behalf.

    

    (structure)

      

      Describes an AWS Identity and Access Management (IAM) role that is associated with a DB cluster.

      

      RoleArn -> (string)

        

        The Amazon Resource Name (ARN) of the IAM role that is associated with the DB cluster.

        

        

      Status -> (string)

        

        Describes the state of association between the IAM role and the DB cluster. The Status property returns one of the following values:

         

         
        * ``ACTIVE`` - the IAM role ARN is associated with the DB cluster and can be used to access other AWS services on your behalf. 
         
        * ``PENDING`` - the IAM role ARN is being associated with the DB cluster. 
         
        * ``INVALID`` - the IAM role ARN is associated with the DB cluster, but the DB cluster is unable to assume the IAM role in order to access other AWS services on your behalf. 
         

        

        

      

    

  IAMDatabaseAuthenticationEnabled -> (boolean)

    

    True if mapping of AWS Identity and Access Management (IAM) accounts to database accounts is enabled; otherwise false.

    

    

  CloneGroupId -> (string)

    

    Identifies the clone group to which the DB cluster is associated.

    

    

  ClusterCreateTime -> (timestamp)

    

    Specifies the time when the DB cluster was created, in Universal Coordinated Time (UTC).

    

    

  

