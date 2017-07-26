[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds delete-db-cluster:


*****************
delete-db-cluster
*****************



===========
Description
===========



The delete-db-cluster action deletes a previously provisioned DB cluster. A successful response from the web service indicates the request was received correctly. When you delete a DB cluster, all automated backups for that DB cluster are deleted and cannot be recovered. Manual DB cluster snapshots of the DB cluster to be deleted are not deleted. 

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    delete-db-cluster
  --db-cluster-identifier <value>
  [--skip-final-snapshot | --no-skip-final-snapshot]
  [--final-db-snapshot-identifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-cluster-identifier`` (string)


  The DB cluster identifier for the DB cluster to be deleted. This parameter isn't case-sensitive. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--skip-final-snapshot`` | ``--no-skip-final-snapshot`` (boolean)


  Determines whether a final DB cluster snapshot is created before the DB cluster is deleted. If ``true`` is specified, no DB cluster snapshot is created. If ``false`` is specified, a DB cluster snapshot is created before the DB cluster is deleted. 

   

  .. note::

    You must specify a ``FinalDBSnapshotIdentifier`` parameter if ``SkipFinalSnapshot`` is ``false`` .

   

  Default: ``false`` 

  

``--final-db-snapshot-identifier`` (string)


  The DB cluster snapshot identifier of the new DB cluster snapshot created when ``SkipFinalSnapshot`` is set to ``false`` . 

   

  .. note::

    Specifying this parameter and also setting the ``SkipFinalShapshot`` parameter to true results in an error. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

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
