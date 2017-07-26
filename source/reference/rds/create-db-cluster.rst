[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds create-db-cluster:


*****************
create-db-cluster
*****************



===========
Description
===========



Creates a new Amazon Aurora DB cluster.

 

You can use the ``ReplicationSourceIdentifier`` parameter to create the DB cluster as a Read Replica of another DB cluster or Amazon RDS MySQL DB instance. For cross-region replication where the DB cluster identified by ``ReplicationSourceIdentifier`` is encrypted, you must also specify the ``PreSignedUrl`` parameter.

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html>`_ in the *Amazon RDS User Guide.*  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/CreateDBCluster>`_


========
Synopsis
========

::

    create-db-cluster
  [--availability-zones <value>]
  [--backup-retention-period <value>]
  [--character-set-name <value>]
  [--database-name <value>]
  --db-cluster-identifier <value>
  [--db-cluster-parameter-group-name <value>]
  [--vpc-security-group-ids <value>]
  [--db-subnet-group-name <value>]
  --engine <value>
  [--engine-version <value>]
  [--port <value>]
  [--master-username <value>]
  [--master-user-password <value>]
  [--option-group-name <value>]
  [--preferred-backup-window <value>]
  [--preferred-maintenance-window <value>]
  [--replication-source-identifier <value>]
  [--tags <value>]
  [--storage-encrypted | --no-storage-encrypted]
  [--kms-key-id <value>]
  [--pre-signed-url <value>]
  [--enable-iam-database-authentication | --no-enable-iam-database-authentication]
  [--source-region <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--availability-zones`` (list)


  A list of EC2 Availability Zones that instances in the DB cluster can be created in. For information on regions and Availability Zones, see `Regions and Availability Zones <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RegionsAndAvailabilityZones.html>`_ . 

  



Syntax::

  "string" "string" ...



``--backup-retention-period`` (integer)


  The number of days for which automated backups are retained. You must specify a minimum value of 1.

   

  Default: 1

   

  Constraints:

   

   
  * Must be a value from 1 to 35 
   

  

``--character-set-name`` (string)


  A value that indicates that the DB cluster should be associated with the specified CharacterSet.

  

``--database-name`` (string)


  The name for your database of up to 64 alpha-numeric characters. If you do not provide a name, Amazon RDS will not create a database in the DB cluster you are creating.

  

``--db-cluster-identifier`` (string)


  The DB cluster identifier. This parameter is stored as a lowercase string.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens. 
   
  * First character must be a letter. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   

   

  Example: ``my-cluster1``  

  

``--db-cluster-parameter-group-name`` (string)


  The name of the DB cluster parameter group to associate with this DB cluster. If this argument is omitted, ``default.aurora5.6`` will be used. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

  

``--vpc-security-group-ids`` (list)


  A list of EC2 VPC security groups to associate with this DB cluster.

  



Syntax::

  "string" "string" ...



``--db-subnet-group-name`` (string)


  A DB subnet group to associate with this DB cluster.

   

  Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

   

  Example: ``mySubnetgroup``  

  

``--engine`` (string)


  The name of the database engine to be used for this DB cluster.

   

  Valid Values: ``aurora``  

  

``--engine-version`` (string)


  The version number of the database engine to use.

   

   **Aurora**  

   

  Example: ``5.6.10a``  

  

``--port`` (integer)


  The port number on which the instances in the DB cluster accept connections.

   

  Default: ``3306``  

  

``--master-username`` (string)


  The name of the master user for the DB cluster.

   

  Constraints:

   

   
  * Must be 1 to 16 alphanumeric characters. 
   
  * First character must be a letter. 
   
  * Cannot be a reserved word for the chosen database engine. 
   

  

``--master-user-password`` (string)


  The password for the master database user. This password can contain any printable ASCII character except "/", """, or "@".

   

  Constraints: Must contain from 8 to 41 characters.

  

``--option-group-name`` (string)


  A value that indicates that the DB cluster should be associated with the specified option group.

   

  Permanent options cannot be removed from an option group. The option group cannot be removed from a DB cluster once it is associated with a DB cluster.

  

``--preferred-backup-window`` (string)


  The daily time range during which automated backups are created if automated backups are enabled using the ``BackupRetentionPeriod`` parameter. 

   

  Default: A 30-minute window selected at random from an 8-hour block of time per region. To see the time blocks available, see `Adjusting the Preferred Maintenance Window <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/AdjustingTheMaintenanceWindow.html>`_ in the *Amazon RDS User Guide.*  

   

  Constraints:

   

   
  * Must be in the format ``hh24:mi-hh24:mi`` . 
   
  * Times should be in Universal Coordinated Time (UTC). 
   
  * Must not conflict with the preferred maintenance window. 
   
  * Must be at least 30 minutes. 
   

  

``--preferred-maintenance-window`` (string)


  The weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

   

  Format: ``ddd:hh24:mi-ddd:hh24:mi``  

   

  Default: A 30-minute window selected at random from an 8-hour block of time per region, occurring on a random day of the week. To see the time blocks available, see `Adjusting the Preferred Maintenance Window <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/AdjustingTheMaintenanceWindow.html>`_ in the *Amazon RDS User Guide.*  

   

  Valid Days: Mon, Tue, Wed, Thu, Fri, Sat, Sun

   

  Constraints: Minimum 30-minute window.

  

``--replication-source-identifier`` (string)


  The Amazon Resource Name (ARN) of the source DB instance or DB cluster if this DB cluster is created as a Read Replica.

  

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



``--storage-encrypted`` | ``--no-storage-encrypted`` (boolean)


  Specifies whether the DB cluster is encrypted.

  

``--kms-key-id`` (string)


  The KMS key identifier for an encrypted DB cluster.

   

  The KMS key identifier is the Amazon Resource Name (ARN) for the KMS encryption key. If you are creating a DB cluster with the same AWS account that owns the KMS encryption key used to encrypt the new DB cluster, then you can use the KMS key alias instead of the ARN for the KMS encryption key.

   

  If the ``StorageEncrypted`` parameter is true, and you do not specify a value for the ``KmsKeyId`` parameter, then Amazon RDS will use your default encryption key. AWS KMS creates the default encryption key for your AWS account. Your AWS account has a different default encryption key for each AWS region.

   

  If you create a Read Replica of an encrypted DB cluster in another region, you must set ``KmsKeyId`` to a KMS key ID that is valid in the destination region. This key is used to encrypt the Read Replica in that region.

  

``--pre-signed-url`` (string)


  A URL that contains a Signature Version 4 signed request for the ``create-db-cluster`` action to be called in the source region where the DB cluster will be replicated from. You only need to specify ``PreSignedUrl`` when you are performing cross-region replication from an encrypted DB cluster.

   

  The pre-signed URL must be a valid request for the ``create-db-cluster`` API action that can be executed in the source region that contains the encrypted DB cluster to be copied.

   

  The pre-signed URL request must contain the following parameter values:

   

   
  * ``KmsKeyId`` - The KMS key identifier for the key to use to encrypt the copy of the DB cluster in the destination region. This should refer to the same KMS key for both the ``create-db-cluster`` action that is called in the destination region, and the action contained in the pre-signed URL. 
   
  * ``DestinationRegion`` - The name of the region that Aurora Read Replica will be created in. 
   
  * ``ReplicationSourceIdentifier`` - The DB cluster identifier for the encrypted DB cluster to be copied. This identifier must be in the Amazon Resource Name (ARN) format for the source region. For example, if you are copying an encrypted DB cluster from the us-west-2 region, then your ``ReplicationSourceIdentifier`` would look like Example: ``arn:aws:rds:us-west-2:123456789012:cluster:aurora-cluster1`` . 
   

   

  To learn how to generate a Signature Version 4 signed request, see `Authenticating Requests\: Using Query Parameters (AWS Signature Version 4) <http://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-query-string-auth.html>`_ and `Signature Version 4 Signing Process <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

  

``--enable-iam-database-authentication`` | ``--no-enable-iam-database-authentication`` (boolean)


  A Boolean value that is true to enable mapping of AWS Identity and Access Management (IAM) accounts to database accounts, and otherwise false.

   

  Default: ``false``  

  

``--source-region`` (string)


  The ID of the region that contains the source for the db cluster.

  

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

    

    

  

