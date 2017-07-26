[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds create-db-instance-read-replica:


*******************************
create-db-instance-read-replica
*******************************



===========
Description
===========



Creates a DB instance for a DB instance running MySQL, MariaDB, or PostgreSQL that acts as a Read Replica of a source DB instance.

 

.. note::

   

  Amazon Aurora does not support this action. You must call the ``create-db-instance`` action to create a DB instance for an Aurora DB cluster.

   

 

All Read Replica DB instances are created as Single-AZ deployments with backups disabled. All other DB instance attributes (including DB security groups and DB parameter groups) are inherited from the source DB instance, except as specified below.

 

.. warning::

   

  The source DB instance must have backup retention enabled.

   

 

You can create an encrypted Read Replica in a different AWS Region than the source DB instance. In that case, the region where you call the ``create-db-instance-read-replica`` action is the destination region of the encrypted Read Replica. The source DB instance must be encrypted.

 

To create an encrypted Read Replica in another AWS Region, you must provide the following values:

 

 
* ``KmsKeyId`` - The AWS Key Management System (KMS) key identifier for the key to use to encrypt the Read Replica in the destination region. 
 
* ``PreSignedUrl`` - A URL that contains a Signature Version 4 signed request for the ``create-db-instance-read-replica`` API action in the AWS region that contains the source DB instance. The ``PreSignedUrl`` parameter must be used when encrypting a Read Replica from another AWS region. The presigned URL must be a valid request for the ``create-db-instance-read-replica`` API action that can be executed in the source region that contains the encrypted DB instance. The presigned URL request must contain the following parameter values: 

   
  * ``DestinationRegion`` - The AWS Region that the Read Replica is created in. This region is the same one where the ``create-db-instance-read-replica`` action is called that contains this presigned URL.  For example, if you create an encrypted Read Replica in the us-east-1 region, and the source DB instance is in the west-2 region, then you call the ``create-db-instance-read-replica`` action in the us-east-1 region and provide a presigned URL that contains a call to the ``create-db-instance-read-replica`` action in the us-west-2 region. For this example, the ``DestinationRegion`` in the presigned URL must be set to the us-east-1 region. 
   
  * ``KmsKeyId`` - The KMS key identifier for the key to use to encrypt the Read Replica in the destination region. This is the same identifier for both the ``create-db-instance-read-replica`` action that is called in the destination region, and the action contained in the presigned URL. 
   
  * ``SourceDBInstanceIdentifier`` - The DB instance identifier for the encrypted Read Replica to be created. This identifier must be in the Amazon Resource Name (ARN) format for the source region. For example, if you create an encrypted Read Replica from a DB instance in the us-west-2 region, then your ``SourceDBInstanceIdentifier`` would look like this example: ``arn:aws:rds:us-west-2:123456789012:instance:mysql-instance1-instance-20161115`` . 
   

 

To learn how to generate a Signature Version 4 signed request, see `Authenticating Requests\: Using Query Parameters (AWS Signature Version 4) <http://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-query-string-auth.html>`_ and `Signature Version 4 Signing Process <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

 
 
* ``DBInstanceIdentifier`` - The identifier for the encrypted Read Replica in the destination region. 
 
* ``SourceDBInstanceIdentifier`` - The DB instance identifier for the encrypted Read Replica. This identifier must be in the ARN format for the source region and is the same value as the ``SourceDBInstanceIdentifier`` in the presigned URL.  
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/CreateDBInstanceReadReplica>`_


========
Synopsis
========

::

    create-db-instance-read-replica
  --db-instance-identifier <value>
  --source-db-instance-identifier <value>
  [--db-instance-class <value>]
  [--availability-zone <value>]
  [--port <value>]
  [--auto-minor-version-upgrade | --no-auto-minor-version-upgrade]
  [--iops <value>]
  [--option-group-name <value>]
  [--publicly-accessible | --no-publicly-accessible]
  [--tags <value>]
  [--db-subnet-group-name <value>]
  [--storage-type <value>]
  [--copy-tags-to-snapshot | --no-copy-tags-to-snapshot]
  [--monitoring-interval <value>]
  [--monitoring-role-arn <value>]
  [--kms-key-id <value>]
  [--pre-signed-url <value>]
  [--enable-iam-database-authentication | --no-enable-iam-database-authentication]
  [--source-region <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-instance-identifier`` (string)


  The DB instance identifier of the Read Replica. This identifier is the unique key that identifies a DB instance. This parameter is stored as a lowercase string.

  

``--source-db-instance-identifier`` (string)


  The identifier of the DB instance that will act as the source for the Read Replica. Each DB instance can have up to five Read Replicas.

   

  Constraints:

   

   
  * Must be the identifier of an existing MySQL, MariaDB, or PostgreSQL DB instance. 
   
  * Can specify a DB instance that is a MySQL Read Replica only if the source is running MySQL 5.6. 
   
  * Can specify a DB instance that is a PostgreSQL DB instance only if the source is running PostgreSQL 9.3.5 or later. 
   
  * The specified DB instance must have automatic backups enabled, its backup retention period must be greater than 0. 
   
  * If the source DB instance is in the same region as the Read Replica, specify a valid DB instance identifier. 
   
  * If the source DB instance is in a different region than the Read Replica, specify a valid DB instance ARN. For more information, go to `Constructing a Amazon RDS Amazon Resource Name (ARN) <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.ARN.html#USER_Tagging.ARN.Constructing>`_ . 
   

  

``--db-instance-class`` (string)


  The compute and memory capacity of the Read Replica. Note that not all instance classes are available in all regions for all DB engines.

   

  Valid Values: ``db.m1.small | db.m1.medium | db.m1.large | db.m1.xlarge | db.m2.xlarge |db.m2.2xlarge | db.m2.4xlarge | db.m3.medium | db.m3.large | db.m3.xlarge | db.m3.2xlarge | db.m4.large | db.m4.xlarge | db.m4.2xlarge | db.m4.4xlarge | db.m4.10xlarge | db.r3.large | db.r3.xlarge | db.r3.2xlarge | db.r3.4xlarge | db.r3.8xlarge | db.t2.micro | db.t2.small | db.t2.medium | db.t2.large``  

   

  Default: Inherits from the source DB instance.

  

``--availability-zone`` (string)


  The Amazon EC2 Availability Zone that the Read Replica will be created in.

   

  Default: A random, system-chosen Availability Zone in the endpoint's region.

   

  Example: ``us-east-1d``  

  

``--port`` (integer)


  The port number that the DB instance uses for connections.

   

  Default: Inherits from the source DB instance

   

  Valid Values: ``1150-65535``  

  

``--auto-minor-version-upgrade`` | ``--no-auto-minor-version-upgrade`` (boolean)


  Indicates that minor engine upgrades will be applied automatically to the Read Replica during the maintenance window.

   

  Default: Inherits from the source DB instance

  

``--iops`` (integer)


  The amount of Provisioned IOPS (input/output operations per second) to be initially allocated for the DB instance.

  

``--option-group-name`` (string)


  The option group the DB instance will be associated with. If omitted, the default option group for the engine specified will be used.

  

``--publicly-accessible`` | ``--no-publicly-accessible`` (boolean)


  Specifies the accessibility options for the DB instance. A value of true specifies an Internet-facing instance with a publicly resolvable DNS name, which resolves to a public IP address. A value of false specifies an internal instance with a DNS name that resolves to a private IP address.

   

  Default: The default behavior varies depending on whether a VPC has been requested or not. The following list shows the default behavior in each case.

   

   
  * **Default VPC:** true 
   
  * **VPC:** false 
   

   

  If no DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be publicly accessible. If a specific DB subnet group has been specified as part of the request and the PubliclyAccessible value has not been set, the DB instance will be private.

  

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



``--db-subnet-group-name`` (string)


  Specifies a DB subnet group for the DB instance. The new DB instance will be created in the VPC associated with the DB subnet group. If no DB subnet group is specified, then the new DB instance is not created in a VPC.

   

  Constraints:

   

   
  * Can only be specified if the source DB instance identifier specifies a DB instance in another region. 
   
  * The specified DB subnet group must be in the same region in which the operation is running. 
   
  * All Read Replicas in one region that are created from the same source DB instance must either: 

     
    * Specify DB subnet groups from the same VPC. All these Read Replicas will be created in the same VPC. 
     
    * Not specify a DB subnet group. All these Read Replicas will be created outside of any VPC. 
     

   
   

   

  Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

   

  Example: ``mySubnetgroup``  

  

``--storage-type`` (string)


  Specifies the storage type to be associated with the Read Replica.

   

  Valid values: ``standard | gp2 | io1``  

   

  If you specify ``io1`` , you must also include a value for the ``Iops`` parameter. 

   

  Default: ``io1`` if the ``Iops`` parameter is specified; otherwise ``standard``  

  

``--copy-tags-to-snapshot`` | ``--no-copy-tags-to-snapshot`` (boolean)


  True to copy all tags from the Read Replica to snapshots of the Read Replica; otherwise false. The default is false.

  

``--monitoring-interval`` (integer)


  The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the Read Replica. To disable collecting Enhanced Monitoring metrics, specify 0. The default is 0.

   

  If ``MonitoringRoleArn`` is specified, then you must also set ``MonitoringInterval`` to a value other than 0.

   

  Valid Values: ``0, 1, 5, 10, 15, 30, 60``  

  

``--monitoring-role-arn`` (string)


  The ARN for the IAM role that permits RDS to send enhanced monitoring metrics to CloudWatch Logs. For example, ``arn:aws:iam:123456789012:role/emaccess`` . For information on creating a monitoring role, go to `To create an IAM role for Amazon RDS Enhanced Monitoring <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Monitoring.html#USER_Monitoring.OS.IAMRole>`_ .

   

  If ``MonitoringInterval`` is set to a value other than 0, then you must supply a ``MonitoringRoleArn`` value.

  

``--kms-key-id`` (string)


  The AWS KMS key ID for an encrypted Read Replica. The KMS key ID is the Amazon Resource Name (ARN), KMS key identifier, or the KMS key alias for the KMS encryption key. 

   

  If you create an unencrypted Read Replica and specify a value for the ``KmsKeyId`` parameter, Amazon RDS encrypts the target Read Replica using the specified KMS encryption key. 

   

  If you create an encrypted Read Replica from your AWS account, you can specify a value for ``KmsKeyId`` to encrypt the Read Replica with a new KMS encryption key. If you don't specify a value for ``KmsKeyId`` , then the Read Replica is encrypted with the same KMS key as the source DB instance. 

   

  If you create an encrypted Read Replica in a different AWS region, then you must specify a KMS key for the destination AWS region. KMS encryption keys are specific to the region that they are created in, and you cannot use encryption keys from one region in another region.

  

``--pre-signed-url`` (string)


  The URL that contains a Signature Version 4 signed request for the ``create-db-instance-read-replica`` API action in the AWS region that contains the source DB instance. The ``PreSignedUrl`` parameter must be used when encrypting a Read Replica from another AWS region.

   

  The presigned URL must be a valid request for the ``create-db-instance-read-replica`` API action that can be executed in the source region that contains the encrypted DB instance. The presigned URL request must contain the following parameter values:

   

   
  * ``DestinationRegion`` - The AWS Region that the Read Replica is created in. This region is the same one where the ``create-db-instance-read-replica`` action is called that contains this presigned URL.  For example, if you create an encrypted Read Replica in the us-east-1 region, and the source DB instance is in the west-2 region, then you call the ``create-db-instance-read-replica`` action in the us-east-1 region and provide a presigned URL that contains a call to the ``create-db-instance-read-replica`` action in the us-west-2 region. For this example, the ``DestinationRegion`` in the presigned URL must be set to the us-east-1 region. 
   
  * ``KmsKeyId`` - The KMS key identifier for the key to use to encrypt the Read Replica in the destination region. This is the same identifier for both the ``create-db-instance-read-replica`` action that is called in the destination region, and the action contained in the presigned URL. 
   
  * ``SourceDBInstanceIdentifier`` - The DB instance identifier for the encrypted Read Replica to be created. This identifier must be in the Amazon Resource Name (ARN) format for the source region. For example, if you create an encrypted Read Replica from a DB instance in the us-west-2 region, then your ``SourceDBInstanceIdentifier`` would look like this example: ``arn:aws:rds:us-west-2:123456789012:instance:mysql-instance1-instance-20161115`` . 
   

   

  To learn how to generate a Signature Version 4 signed request, see `Authenticating Requests\: Using Query Parameters (AWS Signature Version 4) <http://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-query-string-auth.html>`_ and `Signature Version 4 Signing Process <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

  

``--enable-iam-database-authentication`` | ``--no-enable-iam-database-authentication`` (boolean)


  True to enable mapping of AWS Identity and Access Management (IAM) accounts to database accounts; otherwise false.

   

  You can enable IAM database authentication for the following database engines

   

   
  * For MySQL 5.6, minor version 5.6.34 or higher 
   
  * For MySQL 5.7, minor version 5.7.16 or higher 
   
  * Aurora 5.6 or higher. 
   

   

  Default: ``false``  

  

``--source-region`` (string)


  The ID of the region that contains the source for the read replica.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DBInstance -> (structure)

  

  Contains the result of a successful invocation of the following actions:

   

   
  *  create-db-instance   
   
  *  delete-db-instance   
   
  *  modify-db-instance   
   
  *  stop-db-instance   
   
  *  start-db-instance   
   

   

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

     

     **MySQL, MariaDB, SQL Server, PostgreSQL**  

     

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

    

    Provides a list of VPC security group elements that the DB instance belongs to.

    

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

          

          

        

      

    DBSubnetGroupArn -> (string)

      

      The Amazon Resource Name (ARN) for the DB subnet group.

      

      

    

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

      

      

    LicenseModel -> (string)

      

      The license model for the DB instance.

       

      Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license``  

      

      

    Iops -> (integer)

      

      Specifies the new Provisioned IOPS value for the DB instance that will be applied or is being applied.

      

      

    DBInstanceIdentifier -> (string)

      

      Contains the new ``DBInstanceIdentifier`` for the DB instance that will be applied or is in progress. 

      

      

    StorageType -> (string)

      

      Specifies the storage type to be associated with the DB instance.

      

      

    CACertificateIdentifier -> (string)

      

      Specifies the identifier of the CA certificate for the DB instance.

      

      

    DBSubnetGroupName -> (string)

      

      The new DB subnet group for the DB instance. 

      

      

    

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

      

      

    

  ReadReplicaDBClusterIdentifiers -> (list)

    

    Contains one or more identifiers of Aurora DB clusters that are Read Replicas of this DB instance.

    

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

    

    The ARN from the key store with which the instance is associated for TDE encryption.

    

    

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

    

    

  DomainMemberships -> (list)

    

    The Active Directory Domain membership records associated with the DB instance.

    

    (structure)

      

      An Active Directory Domain membership record associated with the DB instance.

      

      Domain -> (string)

        

        The identifier of the Active Directory Domain.

        

        

      Status -> (string)

        

        The status of the DB instance's Active Directory Domain membership, such as joined, pending-join, failed etc).

        

        

      FQDN -> (string)

        

        The fully qualified domain name of the Active Directory Domain.

        

        

      IAMRoleName -> (string)

        

        The name of the IAM role to be used when making API calls to the Directory Service.

        

        

      

    

  CopyTagsToSnapshot -> (boolean)

    

    Specifies whether tags are copied from the DB instance to snapshots of the DB instance.

    

    

  MonitoringInterval -> (integer)

    

    The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance.

    

    

  EnhancedMonitoringResourceArn -> (string)

    

    The Amazon Resource Name (ARN) of the Amazon CloudWatch Logs log stream that receives the Enhanced Monitoring metrics data for the DB instance.

    

    

  MonitoringRoleArn -> (string)

    

    The ARN for the IAM role that permits RDS to send Enhanced Monitoring metrics to CloudWatch Logs.

    

    

  PromotionTier -> (integer)

    

    A value that specifies the order in which an Aurora Replica is promoted to the primary instance after a failure of the existing primary instance. For more information, see `Fault Tolerance for an Aurora DB Cluster <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Aurora.Managing.html#Aurora.Managing.FaultTolerance>`_ . 

    

    

  DBInstanceArn -> (string)

    

    The Amazon Resource Name (ARN) for the DB instance.

    

    

  Timezone -> (string)

    

    The time zone of the DB instance. In most cases, the ``Timezone`` element is empty. ``Timezone`` content appears only for Microsoft SQL Server DB instances that were created with a time zone specified. 

    

    

  IAMDatabaseAuthenticationEnabled -> (boolean)

    

    True if mapping of AWS Identity and Access Management (IAM) accounts to database accounts is enabled; otherwise false.

     

    IAM database authentication can be enabled for the following database engines

     

     
    * For MySQL 5.6, minor version 5.6.34 or higher 
     
    * For MySQL 5.7, minor version 5.7.16 or higher 
     
    * Aurora 5.6 or higher. To enable IAM database authentication for Aurora, see DBCluster Type. 
     

    

    

  

