[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds reboot-db-instance:


******************
reboot-db-instance
******************



===========
Description
===========



Rebooting a DB instance restarts the database engine service. A reboot also applies to the DB instance any modifications to the associated DB parameter group that were pending. Rebooting a DB instance results in a momentary outage of the instance, during which the DB instance status is set to rebooting. If the RDS instance is configured for MultiAZ, it is possible that the reboot will be conducted through a failover. An Amazon RDS event is created when the reboot is completed. 

 

If your DB instance is deployed in multiple Availability Zones, you can force a failover from one AZ to the other during the reboot. You might force a failover to test the availability of your DB instance deployment or to restore operations to the original AZ after a failover occurs. 

 

The time required to reboot is a function of the specific database engine's crash recovery process. To improve the reboot time, we recommend that you reduce database activities as much as possible during the reboot process to reduce rollback activity for in-transit transactions. 



========
Synopsis
========

::

    reboot-db-instance
  --db-instance-identifier <value>
  [--force-failover | --no-force-failover]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-instance-identifier`` (string)


  The DB instance identifier. This parameter is stored as a lowercase string. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--force-failover`` | ``--no-force-failover`` (boolean)


  When ``true`` , the reboot will be conducted through a MultiAZ failover. 

   

  Constraint: You cannot specify ``true`` if the instance is not configured for MultiAZ.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DBInstance -> (structure)

  

  Contains the result of a successful invocation of the following actions: 

   

   
  *  create-db-instance  
   
  *  delete-db-instance  
   
  *  modify-db-instance  
   

   

  This data type is used as a response element in the  describe-db-instances action.

  

  DBInstanceIdentifier -> (string)

    

    Contains a user-supplied database identifier. This identifier is the unique key that identifies a DB instance. 

    

    

  DBInstanceClass -> (string)

    

    Contains the name of the compute and memory capacity class of the DB instance. 

    

    

  Engine -> (string)

    

    Provides the name of the database engine to be used for this DB instance. 

    

    

  DBInstanceStatus -> (string)

    

    Specifies the current state of this database. 

    

    

  MasterUsername -> (string)

    

    Contains the master username for the DB instance. 

    

    

  DBName -> (string)

    

    The meaning of this parameter differs according to the database engine you use. For example, this value returns MySQL, MariaDB, or PostgreSQL information when returning values from create-db-instance-read-replica since Read Replicas are only supported for these engines.

     

     **MySQL, MariaDB, SQL Server, PostgreSQL, Amazon Aurora**  

     

    Contains the name of the initial database of this instance that was provided at create time, if one was specified when the DB instance was created. This same name is returned for the life of the DB instance. 

     

    Type: db-instance-identifier

     

     **Oracle**  

     

    Contains the Oracle System ID (SID) of the created DB instance. Not shown when the returned parameters do not apply to an Oracle DB instance. 

    

    

  Endpoint -> (structure)

    

    Specifies the connection endpoint. 

    

    Address -> (string)

      

      Specifies the DNS address of the DB instance. 

      

      

    Port -> (integer)

      

      Specifies the port that the database engine is listening on. 

      

      

    HostedZoneId -> (string)

      

      Specifies the ID that Amazon Route 53 assigns when you create a hosted zone.

      

      

    

  AllocatedStorage -> (integer)

    

    Specifies the allocated storage size specified in gigabytes. 

    

    

  InstanceCreateTime -> (timestamp)

    

    Provides the date and time the DB instance was created. 

    

    

  PreferredBackupWindow -> (string)

    

    Specifies the daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` . 

    

    

  BackupRetentionPeriod -> (integer)

    

    Specifies the number of days for which automatic DB snapshots are retained. 

    

    

  DBSecurityGroups -> (list)

    

    Provides List of DB security group elements containing only ``DBSecurityGroup.Name`` and ``DBSecurityGroup.Status`` subelements. 

    

    (structure)

      

      This data type is used as a response element in the following actions: 

       

       
      *  modify-db-instance  
       
      *  reboot-db-instance  
       
      *  restore-db-instance-from-db-snapshot  
       
      *  restore-db-instance-to-point-in-time  
       

      

      DBSecurityGroupName -> (string)

        

        The name of the DB security group. 

        

        

      Status -> (string)

        

        The status of the DB security group. 

        

        

      

    

  VpcSecurityGroups -> (list)

    

    Provides List of VPC security group elements that the DB instance belongs to. 

    

    (structure)

      

      This data type is used as a response element for queries on VPC security group membership.

      

      VpcSecurityGroupId -> (string)

        

        The name of the VPC security group.

        

        

      Status -> (string)

        

        The status of the VPC security group. 

        

        

      

    

  DBParameterGroups -> (list)

    

    Provides the list of DB parameter groups applied to this DB instance. 

    

    (structure)

      

      The status of the DB parameter group. 

       

      This data type is used as a response element in the following actions:

       

       
      *  create-db-instance  
       
      *  create-db-instance-read-replica  
       
      *  delete-db-instance  
       
      *  modify-db-instance  
       
      *  reboot-db-instance  
       
      *  restore-db-instance-from-db-snapshot  
       

      

      DBParameterGroupName -> (string)

        

        The name of the DP parameter group. 

        

        

      ParameterApplyStatus -> (string)

        

        The status of parameter updates. 

        

        

      

    

  AvailabilityZone -> (string)

    

    Specifies the name of the Availability Zone the DB instance is located in. 

    

    

  DBSubnetGroup -> (structure)

    

    Specifies information on the subnet group associated with the DB instance, including the name, description, and subnets in the subnet group. 

    

    DBSubnetGroupName -> (string)

      

      The name of the DB subnet group. 

      

      

    DBSubnetGroupDescription -> (string)

      

      Provides the description of the DB subnet group. 

      

      

    VpcId -> (string)

      

      Provides the VpcId of the DB subnet group. 

      

      

    SubnetGroupStatus -> (string)

      

      Provides the status of the DB subnet group. 

      

      

    Subnets -> (list)

      

      Contains a list of  Subnet elements. 

      

      (structure)

        

        This data type is used as a response element in the  describe-db-subnet-groups action. 

        

        SubnetIdentifier -> (string)

          

          Specifies the identifier of the subnet. 

          

          

        SubnetAvailabilityZone -> (structure)

          

          Contains Availability Zone information. 

           

          This data type is used as an element in the following data type: 

          
          *  OrderableDBInstanceOption 
          

          

          

          Name -> (string)

            

            The name of the availability zone. 

            

            

          

        SubnetStatus -> (string)

          

          Specifies the status of the subnet. 

          

          

        

      

    

  PreferredMaintenanceWindow -> (string)

    

    Specifies the weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC). 

    

    

  PendingModifiedValues -> (structure)

    

    Specifies that changes to the DB instance are pending. This element is only included when changes are pending. Specific changes are identified by subelements. 

    

    DBInstanceClass -> (string)

      

      Contains the new ``DBInstanceClass`` for the DB instance that will be applied or is in progress. 

      

      

    AllocatedStorage -> (integer)

      

      Contains the new ``AllocatedStorage`` size for the DB instance that will be applied or is in progress. 

      

      

    MasterUserPassword -> (string)

      

      Contains the pending or in-progress change of the master credentials for the DB instance. 

      

      

    Port -> (integer)

      

      Specifies the pending port for the DB instance. 

      

      

    BackupRetentionPeriod -> (integer)

      

      Specifies the pending number of days for which automated backups are retained. 

      

      

    MultiAZ -> (boolean)

      

      Indicates that the Single-AZ DB instance is to change to a Multi-AZ deployment. 

      

      

    EngineVersion -> (string)

      

      Indicates the database engine version. 

      

      

    Iops -> (integer)

      

      Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied. 

      

      

    DBInstanceIdentifier -> (string)

      

      Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

      

      

    StorageType -> (string)

      

      Specifies the storage type to be associated with the DB instance. 

      

      

    CACertificateIdentifier -> (string)

      

      Specifies the identifier of the CA certificate for the DB instance.

      

      

    

  LatestRestorableTime -> (timestamp)

    

    Specifies the latest time to which a database can be restored with point-in-time restore. 

    

    

  MultiAZ -> (boolean)

    

    Specifies if the DB instance is a Multi-AZ deployment. 

    

    

  EngineVersion -> (string)

    

    Indicates the database engine version. 

    

    

  AutoMinorVersionUpgrade -> (boolean)

    

    Indicates that minor version patches are applied automatically. 

    

    

  ReadReplicaSourceDBInstanceIdentifier -> (string)

    

    Contains the identifier of the source DB instance if this DB instance is a Read Replica. 

    

    

  ReadReplicaDBInstanceIdentifiers -> (list)

    

    Contains one or more identifiers of the Read Replicas associated with this DB instance. 

    

    (string)

      

      

    

  LicenseModel -> (string)

    

    License model information for this DB instance. 

    

    

  Iops -> (integer)

    

    Specifies the Provisioned IOPS (I/O operations per second) value. 

    

    

  OptionGroupMemberships -> (list)

    

    Provides the list of option group memberships for this DB instance. 

    

    (structure)

      

      Provides information on the option groups the DB instance is a member of. 

      

      OptionGroupName -> (string)

        

        The name of the option group that the instance belongs to. 

        

        

      Status -> (string)

        

        The status of the DB instance's option group membership. Valid values are: ``in-sync`` , ``pending-apply`` , ``pending-removal`` , ``pending-maintenance-apply`` , ``pending-maintenance-removal`` , ``applying`` , ``removing`` , and ``failed`` . 

        

        

      

    

  CharacterSetName -> (string)

    

    If present, specifies the name of the character set that this instance is associated with. 

    

    

  SecondaryAvailabilityZone -> (string)

    

    If present, specifies the name of the secondary Availability Zone for a DB instance with multi-AZ support. 

    

    

  PubliclyAccessible -> (boolean)

    

    Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address. 

     

    Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case. 

     

     
    * **Default VPC:** true
     
    * **VPC:** false
     

     

    If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private. 

    

    

  StatusInfos -> (list)

    

    The status of a Read Replica. If the instance is not a Read Replica, this will be blank. 

    

    (structure)

      

      Provides a list of status information for a DB instance.

      

      StatusType -> (string)

        

        This value is currently "read replication." 

        

        

      Normal -> (boolean)

        

        Boolean value that is true if the instance is operating normally, or false if the instance is in an error state. 

        

        

      Status -> (string)

        

        Status of the DB instance. For a StatusType of read replica, the values can be replicating, error, stopped, or terminated. 

        

        

      Message -> (string)

        

        Details of the error if there is an error for the instance. If the instance is not in an error state, this value is blank. 

        

        

      

    

  StorageType -> (string)

    

    Specifies the storage type associated with DB instance. 

    

    

  TdeCredentialArn -> (string)

    

    The ARN from the Key Store with which the instance is associated for TDE encryption. 

    

    

  DbInstancePort -> (integer)

    

    Specifies the port that the DB instance listens on. If the DB instance is part of a DB cluster, this can be a different port than the DB cluster port. 

    

    

  DBClusterIdentifier -> (string)

    

    If the DB instance is a member of a DB cluster, contains the name of the DB cluster that the DB instance is a member of.

    

    

  StorageEncrypted -> (boolean)

    

    Specifies whether the DB instance is encrypted. 

    

    

  KmsKeyId -> (string)

    

    If ``StorageEncrypted`` is true, the KMS key identifier for the encrypted DB instance. 

    

    

  DbiResourceId -> (string)

    

    The region-unique, immutable identifier for the DB instance. This identifier is found in AWS CloudTrail log entries whenever the KMS key for the DB instance is accessed. 

    

    

  CACertificateIdentifier -> (string)

    

    The identifier of the CA certificate for this DB instance.

    

    

  CopyTagsToSnapshot -> (boolean)

    

    Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

    

    

  MonitoringInterval -> (integer)

    

    The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

    

    

  EnhancedMonitoringResourceArn -> (string)

    

    The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

    

    

  MonitoringRoleArn -> (string)

    

    The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

    

    

  

