[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds failover-db-cluster:


*******************
failover-db-cluster
*******************



===========
Description
===========



Forces a failover for a DB cluster.

 

A failover for a DB cluster promotes one of the Aurora Replicas (read-only instances) in the DB cluster to be the primary instance (the cluster writer).

 

Amazon Aurora will automatically fail over to an Aurora Replica, if one exists, when the primary instance fails. You can force a failover when you want to simulate a failure of a primary instance for testing. Because each instance in a DB cluster has its own endpoint address, you will need to clean up and re-establish any existing connections that use those endpoint addresses when the failover is complete.

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html>`_ in the *Amazon RDS User Guide.*  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/FailoverDBCluster>`_


========
Synopsis
========

::

    failover-db-cluster
  [--db-cluster-identifier <value>]
  [--target-db-instance-identifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-cluster-identifier`` (string)


  A DB cluster identifier to force a failover for. This parameter is not case-sensitive.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

  

``--target-db-instance-identifier`` (string)


  The name of the instance to promote to the primary instance.

   

  You must specify the instance identifier for an Aurora Replica in the DB cluster. For example, ``mydbcluster-replica1`` .

  

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

    

    

  

