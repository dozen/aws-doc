[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds modify-db-cluster:


*****************
modify-db-cluster
*****************



===========
Description
===========



Modify a setting for an Amazon Aurora DB cluster. You can change one or more database configuration parameters by specifying these parameters and the new values in the request. For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    modify-db-cluster
  --db-cluster-identifier <value>
  [--new-db-cluster-identifier <value>]
  [--apply-immediately | --no-apply-immediately]
  [--backup-retention-period <value>]
  [--db-cluster-parameter-group-name <value>]
  [--vpc-security-group-ids <value>]
  [--port <value>]
  [--master-user-password <value>]
  [--option-group-name <value>]
  [--preferred-backup-window <value>]
  [--preferred-maintenance-window <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-cluster-identifier`` (string)


  The DB cluster identifier for the cluster being modified. This parameter is not case-sensitive. 

   

  Constraints:

   

   
  * Must be the identifier for an existing DB cluster.
   
  * Must contain from 1 to 63 alphanumeric characters or hyphens.
   
  * First character must be a letter.
   
  * Cannot end with a hyphen or contain two consecutive hyphens.
   

  

``--new-db-cluster-identifier`` (string)


  The new DB cluster identifier for the DB cluster when renaming a DB cluster. This value is stored as a lowercase string. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

   

  Example: ``my-cluster2`` 

  

``--apply-immediately`` | ``--no-apply-immediately`` (boolean)


  A value that specifies whether the modifications in this request and any pending modifications are asynchronously applied as soon as possible, regardless of the ``PreferredMaintenanceWindow`` setting for the DB cluster. 

   

  If this parameter is set to ``false`` , changes to the DB cluster are applied during the next maintenance window.

   

  Default: ``false`` 

  

``--backup-retention-period`` (integer)


  The number of days for which automated backups are retained. You must specify a minimum value of 1. 

   

  Default: 1 

   

  Constraints:

   

   
  * Must be a value from 1 to 35
   

  

``--db-cluster-parameter-group-name`` (string)


  The name of the DB cluster parameter group to use for the DB cluster.

  

``--vpc-security-group-ids`` (list)


  A lst of VPC security groups that the DB cluster will belong to. 

  



Syntax::

  "string" "string" ...



``--port`` (integer)


  The port number on which the DB cluster accepts connections. 

   

  Constraints: Value must be ``1150-65535`` 

   

  Default: The same port as the original DB cluster.

  

``--master-user-password`` (string)


  The new password for the master database user. This password can contain any printable ASCII character except "/", """, or "@". 

   

  Constraints: Must contain from 8 to 41 characters. 

  

``--option-group-name`` (string)


  A value that indicates that the DB cluster should be associated with the specified option group. Changing this parameter does not result in an outage except in the following case, and the change is applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. If the parameter change results in an option group that enables OEM, this change can cause a brief (sub-second) period during which new connections are rejected but existing connections are not interrupted. 

   

  Permanent options cannot be removed from an option group. The option group cannot be removed from a DB cluster once it is associated with a DB cluster. 

  

``--preferred-backup-window`` (string)


  The daily time range during which automated backups are created if automated backups are enabled, using the ``BackupRetentionPeriod`` parameter. 

   

  Default: A 30-minute window selected at random from an 8-hour block of time per region. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

   

  Constraints:

   

   
  * Must be in the format ``hh24:mi-hh24:mi`` .
   
  * Times should be in Universal Coordinated Time (UTC).
   
  * Must not conflict with the preferred maintenance window.
   
  * Must be at least 30 minutes.
   

  

``--preferred-maintenance-window`` (string)


  The weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC). 

   

  Format: ``ddd:hh24:mi-ddd:hh24:mi`` 

   

  Default: A 30-minute window selected at random from an 8-hour block of time per region, occurring on a random day of the week. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

   

  Valid Days: Mon, Tue, Wed, Thu, Fri, Sat, Sun

   

  Constraints: Minimum 30-minute window.

  

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
.. _Adjusting the Preferred Maintenance Window: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/AdjustingTheMaintenanceWindow.html
