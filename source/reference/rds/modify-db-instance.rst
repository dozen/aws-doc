[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds modify-db-instance:


******************
modify-db-instance
******************



===========
Description
===========



Modify settings for a DB instance. You can change one or more database configuration parameters by specifying these parameters and the new values in the request. 



========
Synopsis
========

::

    modify-db-instance
  --db-instance-identifier <value>
  [--allocated-storage <value>]
  [--db-instance-class <value>]
  [--db-security-groups <value>]
  [--vpc-security-group-ids <value>]
  [--apply-immediately | --no-apply-immediately]
  [--master-user-password <value>]
  [--db-parameter-group-name <value>]
  [--backup-retention-period <value>]
  [--preferred-backup-window <value>]
  [--preferred-maintenance-window <value>]
  [--multi-az | --no-multi-az]
  [--engine-version <value>]
  [--allow-major-version-upgrade | --no-allow-major-version-upgrade]
  [--auto-minor-version-upgrade | --no-auto-minor-version-upgrade]
  [--iops <value>]
  [--option-group-name <value>]
  [--new-db-instance-identifier <value>]
  [--storage-type <value>]
  [--tde-credential-arn <value>]
  [--tde-credential-password <value>]
  [--ca-certificate-identifier <value>]
  [--copy-tags-to-snapshot | --no-copy-tags-to-snapshot]
  [--monitoring-interval <value>]
  [--db-port-number <value>]
  [--publicly-accessible | --no-publicly-accessible]
  [--monitoring-role-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-instance-identifier`` (string)


  The DB instance identifier. This value is stored as a lowercase string. 

   

  Constraints:

   

   
  * Must be the identifier for an existing DB instance
   
  * Must contain from 1 to 63 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--allocated-storage`` (integer)


  The new storage capacity of the RDS instance. Changing this setting does not result in an outage and the change is applied during the next maintenance window unless ``ApplyImmediately`` is set to ``true`` for this request. 

   

   **MySQL**  

   

  Default: Uses existing setting

   

  Valid Values: 5-6144

   

  Constraints: Value supplied must be at least 10% greater than the current value. Values that are not at least 10% greater than the existing value are rounded up so that they are 10% greater than the current value.

   

  Type: Integer

   

   **MariaDB**  

   

  Default: Uses existing setting

   

  Valid Values: 5-6144

   

  Constraints: Value supplied must be at least 10% greater than the current value. Values that are not at least 10% greater than the existing value are rounded up so that they are 10% greater than the current value.

   

  Type: Integer

   

   **PostgreSQL**  

   

  Default: Uses existing setting

   

  Valid Values: 5-6144

   

  Constraints: Value supplied must be at least 10% greater than the current value. Values that are not at least 10% greater than the existing value are rounded up so that they are 10% greater than the current value.

   

  Type: Integer

   

   **Oracle**  

   

  Default: Uses existing setting

   

  Valid Values: 10-6144

   

  Constraints: Value supplied must be at least 10% greater than the current value. Values that are not at least 10% greater than the existing value are rounded up so that they are 10% greater than the current value.

   

   **SQL Server**  

   

  Cannot be modified.

   

  If you choose to migrate your DB instance from using standard storage to using Provisioned IOPS, or from using Provisioned IOPS to using standard storage, the process can take time. The duration of the migration depends on several factors such as database load, storage size, storage type (standard or Provisioned IOPS), amount of IOPS provisioned (if any), and the number of prior scale storage operations. Typical migration times are under 24 hours, but the process can take up to several days in some cases. During the migration, the DB instance will be available for use, but might experience performance degradation. While the migration takes place, nightly backups for the instance will be suspended. No other Amazon RDS operations can take place for the instance, including modifying the instance, rebooting the instance, deleting the instance, creating a Read Replica for the instance, and creating a DB snapshot of the instance. 

  

``--db-instance-class`` (string)


  The new compute and memory capacity of the DB instance. To determine the instance classes that are available for a particular DB engine, use the  describe-orderable-db-instance-options action. 

   

  Passing a value for this setting causes an outage during the change and is applied during the next maintenance window, unless ``ApplyImmediately`` is specified as ``true`` for this request. 

   

  Default: Uses existing setting

   

  Valid Values: ``db.t1.micro | db.m1.small | db.m1.medium | db.m1.large | db.m1.xlarge | db.m2.xlarge | db.m2.2xlarge | db.m2.4xlarge | db.m3.medium | db.m3.large | db.m3.xlarge | db.m3.2xlarge | db.m4.large | db.m4.xlarge | db.m4.2xlarge | db.m4.4xlarge | db.m4.10xlarge | db.r3.large | db.r3.xlarge | db.r3.2xlarge | db.r3.4xlarge | db.r3.8xlarge | db.t2.micro | db.t2.small | db.t2.medium | db.t2.large`` 

  

``--db-security-groups`` (list)


  A list of DB security groups to authorize on this DB instance. Changing this setting does not result in an outage and the change is asynchronously applied as soon as possible. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  



Syntax::

  "string" "string" ...



``--vpc-security-group-ids`` (list)


  A list of EC2 VPC security groups to authorize on this DB instance. This change is asynchronously applied as soon as possible. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  



Syntax::

  "string" "string" ...



``--apply-immediately`` | ``--no-apply-immediately`` (boolean)


  Specifies whether the modifications in this request and any pending modifications are asynchronously applied as soon as possible, regardless of the ``PreferredMaintenanceWindow`` setting for the DB instance. 

   

  If this parameter is set to ``false`` , changes to the DB instance are applied during the next maintenance window. Some parameter changes can cause an outage and will be applied on the next call to  reboot-db-instance , or the next failure reboot. Review the table of parameters in `Modifying a DB Instance and Using the Apply Immediately Parameter`_ to see the impact that setting ``ApplyImmediately`` to ``true`` or ``false`` has for each modified parameter and to determine when the changes will be applied. 

   

  Default: ``false`` 

  

``--master-user-password`` (string)


  The new password for the DB instance master user. Can be any printable ASCII character except "/", """, or "@".

   

  Changing this parameter does not result in an outage and the change is asynchronously applied as soon as possible. Between the time of the request and the completion of the request, the ``MasterUserPassword`` element exists in the ``PendingModifiedValues`` element of the operation response. 

   

  Default: Uses existing setting

   

  Constraints: Must be 8 to 41 alphanumeric characters (MySQL, MariaDB, and Amazon Aurora), 8 to 30 alphanumeric characters (Oracle), or 8 to 128 alphanumeric characters (SQL Server).

   

  .. note::

    Amazon RDS API actions never return the password, so this action provides a way to regain access to a primary instance user if the password is lost. This includes restoring privileges that might have been accidentally revoked. 

  

``--db-parameter-group-name`` (string)


  The name of the DB parameter group to apply to the DB instance. Changing this setting does not result in an outage. The parameter group name itself is changed immediately, but the actual parameter changes are not applied until you reboot the instance without failover. The db instance will NOT be rebooted automatically and the parameter changes will NOT be applied during the next maintenance window. 

   

  Default: Uses existing setting

   

  Constraints: The DB parameter group must be in the same DB parameter group family as this DB instance.

  

``--backup-retention-period`` (integer)


  The number of days to retain automated backups. Setting this parameter to a positive number enables backups. Setting this parameter to 0 disables automated backups. 

   

  Changing this parameter can result in an outage if you change from 0 to a non-zero value or from a non-zero value to 0. These changes are applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. If you change the parameter from one non-zero value to another non-zero value, the change is asynchronously applied as soon as possible.

   

  Default: Uses existing setting

   

  Constraints:

   

   
  * Must be a value from 0 to 35
   
  * Can be specified for a MySQL Read Replica only if the source is running MySQL 5.6
   
  * Can be specified for a PostgreSQL Read Replica only if the source is running PostgreSQL 9.3.5
   
  * Cannot be set to 0 if the DB instance is a source to Read Replicas
   

  

``--preferred-backup-window`` (string)


  The daily time range during which automated backups are created if automated backups are enabled, as determined by the ``BackupRetentionPeriod`` parameter. Changing this parameter does not result in an outage and the change is asynchronously applied as soon as possible. 

   

  Constraints:

   

   
  * Must be in the format hh24:mi-hh24:mi
   
  * Times should be in Universal Time Coordinated (UTC)
   
  * Must not conflict with the preferred maintenance window
   
  * Must be at least 30 minutes
   

  

``--preferred-maintenance-window`` (string)


  The weekly time range (in UTC) during which system maintenance can occur, which might result in an outage. Changing this parameter does not result in an outage, except in the following situation, and the change is asynchronously applied as soon as possible. If there are pending actions that cause a reboot, and the maintenance window is changed to include the current time, then changing this parameter will cause a reboot of the DB instance. If moving this window to the current time, there must be at least 30 minutes between the current time and end of the window to ensure pending changes are applied. 

   

  Default: Uses existing setting

   

  Format: ddd:hh24:mi-ddd:hh24:mi

   

  Valid Days: Mon | Tue | Wed | Thu | Fri | Sat | Sun

   

  Constraints: Must be at least 30 minutes

  

``--multi-az`` | ``--no-multi-az`` (boolean)


  Specifies if the DB instance is a Multi-AZ deployment. Changing this parameter does not result in an outage and the change is applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. 

   

  Constraints: Cannot be specified if the DB instance is a Read Replica. This parameter cannot be used with SQL Server DB instances. Multi-AZ for SQL Server DB instances is set using the Mirroring option in an option group associated with the DB instance.

  

``--engine-version`` (string)


  The version number of the database engine to upgrade to. Changing this parameter results in an outage and the change is applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. 

   

  For major version upgrades, if a non-default DB parameter group is currently in use, a new DB parameter group in the DB parameter group family for the new engine version must be specified. The new DB parameter group can be the default for that DB parameter group family. 

   

  For a list of valid engine versions, see  create-db-instance .

  

``--allow-major-version-upgrade`` | ``--no-allow-major-version-upgrade`` (boolean)


  Indicates that major version upgrades are allowed. Changing this parameter does not result in an outage and the change is asynchronously applied as soon as possible. 

   

  Constraints: This parameter must be set to true when specifying a value for the EngineVersion parameter that is a different major version than the DB instance's current version.

  

``--auto-minor-version-upgrade`` | ``--no-auto-minor-version-upgrade`` (boolean)


  Indicates that minor version upgrades will be applied automatically to the DB instance during the maintenance window. Changing this parameter does not result in an outage except in the following case and the change is asynchronously applied as soon as possible. An outage will result if this parameter is set to ``true`` during the maintenance window, and a newer minor version is available, and RDS has enabled auto patching for that engine version. 

  

``--iops`` (integer)


  The new Provisioned IOPS (I/O operations per second) value for the RDS instance. Changing this setting does not result in an outage and the change is applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. 

   

  Default: Uses existing setting

   

  Constraints: Value supplied must be at least 10% greater than the current value. Values that are not at least 10% greater than the existing value are rounded up so that they are 10% greater than the current value. If you are migrating from Provisioned IOPS to standard storage, set this value to 0. The DB instance will require a reboot for the change in storage type to take effect.

   

   **SQL Server**  

   

  Setting the IOPS value for the SQL Server database engine is not supported.

   

  Type: Integer

   

  If you choose to migrate your DB instance from using standard storage to using Provisioned IOPS, or from using Provisioned IOPS to using standard storage, the process can take time. The duration of the migration depends on several factors such as database load, storage size, storage type (standard or Provisioned IOPS), amount of IOPS provisioned (if any), and the number of prior scale storage operations. Typical migration times are under 24 hours, but the process can take up to several days in some cases. During the migration, the DB instance will be available for use, but might experience performance degradation. While the migration takes place, nightly backups for the instance will be suspended. No other Amazon RDS operations can take place for the instance, including modifying the instance, rebooting the instance, deleting the instance, creating a Read Replica for the instance, and creating a DB snapshot of the instance. 

  

``--option-group-name`` (string)


  Indicates that the DB instance should be associated with the specified option group. Changing this parameter does not result in an outage except in the following case and the change is applied during the next maintenance window unless the ``ApplyImmediately`` parameter is set to ``true`` for this request. If the parameter change results in an option group that enables OEM, this change can cause a brief (sub-second) period during which new connections are rejected but existing connections are not interrupted. 

   

  Permanent options, such as the TDE option for Oracle Advanced Security TDE, cannot be removed from an option group, and that option group cannot be removed from a DB instance once it is associated with a DB instance 

  

``--new-db-instance-identifier`` (string)


  The new DB instance identifier for the DB instance when renaming a DB instance. When you change the DB instance identifier, an instance reboot will occur immediately if you set ``Apply Immediately`` to true, or will occur during the next maintenance window if ``Apply Immediately`` to false. This value is stored as a lowercase string. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--storage-type`` (string)


  Specifies the storage type to be associated with the DB instance. 

   

  Valid values: ``standard | gp2 | io1`` 

   

  If you specify ``io1`` , you must also include a value for the ``Iops`` parameter. 

   

  Default: ``io1`` if the ``Iops`` parameter is specified; otherwise ``standard`` 

  

``--tde-credential-arn`` (string)


  The ARN from the Key Store with which to associate the instance for TDE encryption. 

  

``--tde-credential-password`` (string)


  The password for the given ARN from the Key Store in order to access the device. 

  

``--ca-certificate-identifier`` (string)


  Indicates the certificate that needs to be associated with the instance. 

  

``--copy-tags-to-snapshot`` | ``--no-copy-tags-to-snapshot`` (boolean)


  True to copy all tags from the DB instance to snapshots of the DB instance; otherwise false. The default is false.

  

``--monitoring-interval`` (integer)


  The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance. To disable collecting Enhanced Monitoring metrics, specify 0. The default is 60.

   

  If ``MonitoringRoleArn`` is specified, then you must also set ``MonitoringInterval`` to a value other than 0.

   

  Valid Values: ``0, 1, 5, 10, 15, 30, 60`` 

  

``--db-port-number`` (integer)


  The port number on which the database accepts connections. 

   

  The value of the ``DBPortNumber`` parameter must not match any of the port values specified for options in the option group for the DB instance.

   

  Your database will restart when you change the ``DBPortNumber`` value regardless of the value of the ``ApplyImmediately`` parameter.

   

   **MySQL**  

   

  Default: ``3306`` 

   

  Valid Values: ``1150-65535`` 

   

   **MariaDB**  

   

  Default: ``3306`` 

   

  Valid Values: ``1150-65535`` 

   

   **PostgreSQL**  

   

  Default: ``5432`` 

   

  Valid Values: ``1150-65535`` 

   

   **Oracle**  

   

  Default: ``1521`` 

   

  Valid Values: ``1150-65535`` 

   

   **SQL Server**  

   

  Default: ``1433`` 

   

  Valid Values: ``1150-65535`` except for ``1434`` , ``3389`` , ``47001`` , ``49152`` , and ``49152`` through ``49156`` . 

   

   **Amazon Aurora**  

   

  Default: ``3306`` 

   

  Valid Values: ``1150-65535`` 

  

``--publicly-accessible`` | ``--no-publicly-accessible`` (boolean)


  no-allow-major-version-upgrade value that indicates if the DB instance has a publicly resolvable DNS name. Set to ``True`` to make the DB instance Internet-facing with a publicly resolvable DNS name, which resolves to a public IP address. Set to ``False`` to make the DB instance internal with a DNS name that resolves to a private IP address. 

   

  ``PubliclyAccessible`` only applies to DB instances in a VPC. The DB instance must be part of a public subnet and ``PubliclyAccessible`` must be true in order for it to be publicly accessible. 

   

  Changes to the ``PubliclyAccessible`` parameter are applied immediately regardless of the value of the ``ApplyImmediately`` parameter.

   

  Default: false 

  

``--monitoring-role-arn`` (string)


  The ARN for the IAM role that permits RDS to send enhanced monitoring metrics to CloudWatch Logs. For example, ``arn:aws:iam:123456789012:role/emaccess`` . For information on creating a monitoring role, go to `To create an IAM role for Amazon RDS Enhanced Monitoring`_ .

   

  If ``MonitoringInterval`` is set to a value other than 0, then you must supply a ``MonitoringRoleArn`` value.

  

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

     

    Type: monitoring-role-arn

     

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

        

        no-allow-major-version-upgrade value that is true if the instance is operating normally, or false if the instance is in an error state. 

        

        

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

    

    

  



.. _Modifying a DB Instance and Using the Apply Immediately Parameter: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.DBInstance.Modifying.html
.. _To create an IAM role for Amazon RDS Enhanced Monitoring: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Monitoring.html#USER_Monitoring.OS.IAMRole
