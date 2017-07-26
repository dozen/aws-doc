[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds create-db-instance:


******************
create-db-instance
******************



===========
Description
===========



Creates a new DB instance. 



========
Synopsis
========

::

    create-db-instance
  [--db-name <value>]
  --db-instance-identifier <value>
  [--allocated-storage <value>]
  --db-instance-class <value>
  --engine <value>
  [--master-username <value>]
  [--master-user-password <value>]
  [--db-security-groups <value>]
  [--vpc-security-group-ids <value>]
  [--availability-zone <value>]
  [--db-subnet-group-name <value>]
  [--preferred-maintenance-window <value>]
  [--db-parameter-group-name <value>]
  [--backup-retention-period <value>]
  [--preferred-backup-window <value>]
  [--port <value>]
  [--multi-az | --no-multi-az]
  [--engine-version <value>]
  [--auto-minor-version-upgrade | --no-auto-minor-version-upgrade]
  [--license-model <value>]
  [--iops <value>]
  [--option-group-name <value>]
  [--character-set-name <value>]
  [--publicly-accessible | --no-publicly-accessible]
  [--tags <value>]
  [--db-cluster-identifier <value>]
  [--storage-type <value>]
  [--tde-credential-arn <value>]
  [--tde-credential-password <value>]
  [--storage-encrypted | --no-storage-encrypted]
  [--kms-key-id <value>]
  [--copy-tags-to-snapshot | --no-copy-tags-to-snapshot]
  [--monitoring-interval <value>]
  [--monitoring-role-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-name`` (string)


  The meaning of this parameter differs according to the database engine you use.

   

  Type: monitoring-role-arn

   

   **MySQL**  

   

  The name of the database to create when the DB instance is created. If this parameter is not specified, no database is created in the DB instance. 

   

  Constraints:

   

   
  * Must contain 1 to 64 alphanumeric characters
   
  * Cannot be a word reserved by the specified database engine
   

   

   **MariaDB**  

   

  The name of the database to create when the DB instance is created. If this parameter is not specified, no database is created in the DB instance. 

   

  Constraints:

   

   
  * Must contain 1 to 64 alphanumeric characters
   
  * Cannot be a word reserved by the specified database engine
   

   

   **PostgreSQL**  

   

  The name of the database to create when the DB instance is created. If this parameter is not specified, the default "postgres" database is created in the DB instance. 

   

  Constraints:

   

   
  * Must contain 1 to 63 alphanumeric characters
   
  * Must begin with a letter or an underscore. Subsequent characters can be letters, underscores, or digits (0-9).
   
  * Cannot be a word reserved by the specified database engine
   

   

   **Oracle**  

   

  The Oracle System ID (SID) of the created DB instance. 

   

  Default: ``ORCL`` 

   

  Constraints:

   

   
  * Cannot be longer than 8 characters
   

   

   **SQL Server**  

   

  Not applicable. Must be null.

   

   **Amazon Aurora**  

   

  The name of the database to create when the primary instance of the DB cluster is created. If this parameter is not specified, no database is created in the DB instance. 

   

  Constraints:

   

   
  * Must contain 1 to 64 alphanumeric characters
   
  * Cannot be a word reserved by the specified database engine
   

  

``--db-instance-identifier`` (string)


  The DB instance identifier. This parameter is stored as a lowercase string. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens (1 to 15 for SQL Server).
   
  * First character must be a letter.
   
  * Cannot end with a hyphen or contain two consecutive hyphens.
   

   

  Example: ``mydbinstance`` 

  

``--allocated-storage`` (integer)


  The amount of storage (in gigabytes) to be initially allocated for the database instance. 

   

  Type: Integer

   

   **MySQL**  

   

  Constraints: Must be an integer from 5 to 6144.

   

   **MariaDB**  

   

  Constraints: Must be an integer from 5 to 6144.

   

   **PostgreSQL**  

   

  Constraints: Must be an integer from 5 to 6144.

   

   **Oracle**  

   

  Constraints: Must be an integer from 10 to 6144.

   

   **SQL Server**  

   

  Constraints: Must be an integer from 200 to 4096 (Standard Edition and Enterprise Edition) or from 20 to 4096 (Express Edition and Web Edition)

  

``--db-instance-class`` (string)


  The compute and memory capacity of the DB instance. 

   

  Valid Values: ``db.t1.micro | db.m1.small | db.m1.medium | db.m1.large | db.m1.xlarge | db.m2.xlarge |db.m2.2xlarge | db.m2.4xlarge | db.m3.medium | db.m3.large | db.m3.xlarge | db.m3.2xlarge | db.m4.large | db.m4.xlarge | db.m4.2xlarge | db.m4.4xlarge | db.m4.10xlarge | db.r3.large | db.r3.xlarge | db.r3.2xlarge | db.r3.4xlarge | db.r3.8xlarge | db.t2.micro | db.t2.small | db.t2.medium | db.t2.large`` 

  

``--engine`` (string)


  The name of the database engine to be used for this instance. 

   

  Valid Values: ``MySQL`` | ``mariadb`` | ``oracle-se1`` | ``oracle-se`` | ``oracle-ee`` | ``sqlserver-ee`` | ``sqlserver-se`` | ``sqlserver-ex`` | ``sqlserver-web`` | ``postgres`` | ``aurora`` 

   

  Not every database engine is available for every AWS region. 

  

``--master-username`` (string)


  The name of master user for the client DB instance. 

   

   **MySQL**  

   

  Constraints:

   

   
  * Must be 1 to 16 alphanumeric characters.
   
  * First character must be a letter.
   
  * Cannot be a reserved word for the chosen database engine.
   

   

   **MariaDB**  

   

  Constraints:

   

   
  * Must be 1 to 16 alphanumeric characters.
   
  * Cannot be a reserved word for the chosen database engine.
   

   

  Type: monitoring-role-arn

   

   **Oracle**  

   

  Constraints:

   

   
  * Must be 1 to 30 alphanumeric characters.
   
  * First character must be a letter.
   
  * Cannot be a reserved word for the chosen database engine.
   

   

   **SQL Server**  

   

  Constraints:

   

   
  * Must be 1 to 128 alphanumeric characters.
   
  * First character must be a letter.
   
  * Cannot be a reserved word for the chosen database engine.
   

   

   **PostgreSQL**  

   

  Constraints:

   

   
  * Must be 1 to 63 alphanumeric characters.
   
  * First character must be a letter.
   
  * Cannot be a reserved word for the chosen database engine.
   

  

``--master-user-password`` (string)


  The password for the master database user. Can be any printable ASCII character except "/", """, or "@". 

   

  Type: monitoring-role-arn

   

   **MySQL**  

   

  Constraints: Must contain from 8 to 41 characters. 

   

   **MariaDB**  

   

  Constraints: Must contain from 8 to 41 characters. 

   

   **Oracle**  

   

  Constraints: Must contain from 8 to 30 characters. 

   

   **SQL Server**  

   

  Constraints: Must contain from 8 to 128 characters. 

   

   **PostgreSQL**  

   

  Constraints: Must contain from 8 to 128 characters. 

   

   **Amazon Aurora**  

   

  Constraints: Must contain from 8 to 41 characters. 

  

``--db-security-groups`` (list)


  A list of DB security groups to associate with this DB instance. 

   

  Default: The default DB security group for the database engine. 

  



Syntax::

  "string" "string" ...



``--vpc-security-group-ids`` (list)


  A list of EC2 VPC security groups to associate with this DB instance. 

   

  Default: The default EC2 VPC security group for the DB subnet group's VPC. 

  



Syntax::

  "string" "string" ...



``--availability-zone`` (string)


  The EC2 Availability Zone that the database instance will be created in. For information on regions and Availability Zones, see `Regions and Availability Zones`_ . 

   

  Default: A random, system-chosen Availability Zone in the endpoint's region. 

   

  Example: ``us-east-1d`` 

   

  Constraint: The AvailabilityZone parameter cannot be specified if the MultiAZ parameter is set to ``true`` . The specified Availability Zone must be in the same region as the current endpoint. 

  

``--db-subnet-group-name`` (string)


  A DB subnet group to associate with this DB instance. 

   

  If there is no DB subnet group, then it is a non-VPC DB instance. 

  

``--preferred-maintenance-window`` (string)


  The weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC). For more information, see `DB Instance Maintenance`_ . 

   

  Format: ``ddd:hh24:mi-ddd:hh24:mi`` 

   

  Default: A 30-minute window selected at random from an 8-hour block of time per region, occurring on a random day of the week. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

   

  Valid Days: Mon, Tue, Wed, Thu, Fri, Sat, Sun

   

  Constraints: Minimum 30-minute window.

  

``--db-parameter-group-name`` (string)


  The name of the DB parameter group to associate with this DB instance. If this argument is omitted, the default DBParameterGroup for the specified engine will be used. 

   

  Constraints: 

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--backup-retention-period`` (integer)


  The number of days for which automated backups are retained. Setting this parameter to a positive number enables backups. Setting this parameter to 0 disables automated backups. 

   

  Default: 1 

   

  Constraints:

   

   
  * Must be a value from 0 to 35
   
  * Cannot be set to 0 if the DB instance is a source to Read Replicas
   

  

``--preferred-backup-window`` (string)


  The daily time range during which automated backups are created if automated backups are enabled, using the ``BackupRetentionPeriod`` parameter. For more information, see `DB Instance Backups`_ . 

   

  Default: A 30-minute window selected at random from an 8-hour block of time per region. To see the time blocks available, see `Adjusting the Preferred Maintenance Window`_ in the *Amazon RDS User Guide.*  

   

  Constraints: 

   

   
  * Must be in the format ``hh24:mi-hh24:mi`` .
   
  * Times should be in Universal Coordinated Time (UTC).
   
  * Must not conflict with the preferred maintenance window.
   
  * Must be at least 30 minutes.
   

  

``--port`` (integer)


  The port number on which the database accepts connections. 

   

   **MySQL**  

   

  Default: ``3306`` 

   

  Valid Values: ``1150-65535`` 

   

  Type: Integer 

   

   **MariaDB**  

   

  Default: ``3306`` 

   

  Valid Values: ``1150-65535`` 

   

  Type: Integer 

   

   **PostgreSQL**  

   

  Default: ``5432`` 

   

  Valid Values: ``1150-65535`` 

   

  Type: Integer 

   

   **Oracle**  

   

  Default: ``1521`` 

   

  Valid Values: ``1150-65535`` 

   

   **SQL Server**  

   

  Default: ``1433`` 

   

  Valid Values: ``1150-65535`` except for ``1434`` , ``3389`` , ``47001`` , ``49152`` , and ``49152`` through ``49156`` . 

   

   **Amazon Aurora**  

   

  Default: ``3306`` 

   

  Valid Values: ``1150-65535`` 

   

  Type: Integer 

  

``--multi-az`` | ``--no-multi-az`` (boolean)


  Specifies if the DB instance is a Multi-AZ deployment. You cannot set the AvailabilityZone parameter if the MultiAZ parameter is set to true. Do not set this value if you want a Multi-AZ deployment for a SQL Server DB instance. Multi-AZ for SQL Server is set using the Mirroring option in an option group. 

  

``--engine-version`` (string)


  The version number of the database engine to use. 

   

  The following are the database engines and major and minor versions that are available with Amazon RDS. Not every database engine is available for every AWS region. 

   

  **MySQL** 

   

   
  * **Version 5.1 (Only available in the following regions: ap-northeast-1, ap-southeast-1, ap-southeast-2, eu-west-1, sa-east-1, us-west-1, us-west-2):**  ``5.1.73a | 5.1.73b`` 
   
  * **Version 5.5 (Only available in the following regions: ap-northeast-1, ap-southeast-1, ap-southeast-2, eu-west-1, sa-east-1, us-west-1, us-west-2):**  ``5.5.40 | 5.5.40a`` 
   
  * **Version 5.5 (Available in all regions):**  ``5.5.40b | 5.5.41 | 5.5.42`` 
   
  * **Version 5.6 (Available in all regions):**  ``5.6.19a | 5.6.19b | 5.6.21 | 5.6.21b | 5.6.22 | 5.6.23`` 
   
  * **Version 5.7 (Available in all regions):**  ``5.7.10`` 
   

   

  **MariaDB** 

   

   
  * **Version 10.0 (Available in all regions except AWS GovCloud (US) Region (us-gov-west-1)):**  ``10.0.17`` 
   

   

  **Oracle Database Enterprise Edition (oracle-ee)** 

   

   
  * **Version 11.2 (Only available in the following regions: ap-northeast-1, ap-southeast-1, ap-southeast-2, eu-west-1, sa-east-1, us-west-1, us-west-2):**  ``11.2.0.2.v3 | 11.2.0.2.v4 | 11.2.0.2.v5 | 11.2.0.2.v6 | 11.2.0.2.v7`` 
   
  * **Version 11.2 (Available in all regions):**  ``11.2.0.3.v1 | 11.2.0.3.v2 | 11.2.0.3.v3 | 11.2.0.4.v1 | 11.2.0.4.v3 | 11.2.0.4.v4`` 
   
  * **Version 12.1 (Available in all regions):**  ``12.1.0.1.v1 | 12.1.0.1.v2 | 12.1.0.2.v1`` 
   

   

  **Oracle Database Standard Edition (oracle-se)** 

   

   
  * **Version 11.2 (Only available in the following regions: us-west-1):**  ``11.2.0.2.v3 | 11.2.0.2.v4 | 11.2.0.2.v5 | 11.2.0.2.v6 | 11.2.0.2.v7`` 
   
  * **Version 11.2 (Only available in the following regions: eu-central-1, us-west-1):**  ``11.2.0.3.v1 | 11.2.0.3.v2 | 11.2.0.3.v3 | 11.2.0.4.v1 | 11.2.0.4.v3 | 11.2.0.4.v4`` 
   
  * **Version 12.1 (Only available in the following regions: eu-central-1, us-west-1):**  ``12.1.0.1.v1 | 12.1.0.1.v2`` 
   

   

  **Oracle Database Standard Edition One (oracle-se1)** 

   

   
  * **Version 11.2 (Only available in the following regions: us-west-1):**  ``11.2.0.2.v3 | 11.2.0.2.v4 | 11.2.0.2.v5 | 11.2.0.2.v6 | 11.2.0.2.v7`` 
   
  * **Version 11.2 (Only available in the following regions: eu-central-1, us-west-1):**  ``11.2.0.3.v1 | 11.2.0.3.v2 | 11.2.0.3.v3 | 11.2.0.4.v1 | 11.2.0.4.v3 | 11.2.0.4.v4`` 
   
  * **Version 12.1 (Only available in the following regions: eu-central-1, us-west-1):**  ``12.1.0.1.v1 | 12.1.0.1.v2`` 
   

   

  **PostgreSQL** 

   

   
  * **Version 9.3 (Only available in the following regions: ap-northeast-1, ap-southeast-1, ap-southeast-2, eu-west-1, sa-east-1, us-west-1, us-west-2):**  ``9.3.1 | 9.3.2`` 
   
  * **Version 9.3 (Available in all regions):**  ``9.3.3 | 9.3.5 | 9.3.6 | 9.3.9 | 9.3.10`` 
   
  * **Version 9.4 (Available in all regions):**  ``9.4.1 | 9.4.4 | 9.4.5`` 
   

   

  **Microsoft SQL Server Enterprise Edition (sqlserver-ee)** 

   

   
  * **Version 10.50 (Available in all regions):**  ``10.50.2789.0.v1`` 
   
  * **Version 10.50 (Available in all regions):**  ``10.50.6000.34.v1`` 
   
  * **Version 11.00 (Available in all regions):**  ``11.00.2100.60.v1`` 
   
  * **Version 11.00 (Available in all regions):**  ``11.00.5058.0.v1`` 
   

   

  **Microsoft SQL Server Express Edition (sqlserver-ex)** 

   

   
  * **Version 10.50 (Available in all regions):**  ``10.50.2789.0.v1`` 
   
  * **Version 10.50 (Available in all regions):**  ``10.50.6000.34.v1`` 
   
  * **Version 11.00 (Available in all regions):**  ``11.00.2100.60.v1`` 
   
  * **Version 11.00 (Available in all regions):**  ``11.00.5058.0.v1`` 
   
  * **Version 12.00 (Available in all regions):**  ``12.00.4422.0.v1`` 
   

   

  **Microsoft SQL Server Standard Edition (sqlserver-se)** 

   

   
  * **Version 10.50 (Available in all regions):**  ``10.50.2789.0.v1`` 
   
  * **Version 10.50 (Available in all regions):**  ``10.50.6000.34.v1`` 
   
  * **Version 11.00 (Available in all regions):**  ``11.00.2100.60.v1`` 
   
  * **Version 11.00 (Available in all regions):**  ``11.00.5058.0.v1`` 
   
  * **Version 12.00 (Available in all regions):**  ``12.00.4422.0.v1`` 
   

   

  **Microsoft SQL Server Web Edition (sqlserver-web)** 

   

   
  * **Version 10.50 (Available in all regions):**  ``10.50.2789.0.v1`` 
   
  * **Version 10.50 (Available in all regions):**  ``10.50.6000.34.v1`` 
   
  * **Version 11.00 (Available in all regions):**  ``11.00.2100.60.v1`` 
   
  * **Version 11.00 (Available in all regions):**  ``11.00.5058.0.v1`` 
   
  * **Version 12.00 (Available in all regions):**  ``12.00.4422.0.v1`` 
   

  

``--auto-minor-version-upgrade`` | ``--no-auto-minor-version-upgrade`` (boolean)


  Indicates that minor engine upgrades will be applied automatically to the DB instance during the maintenance window. 

   

  Default: ``true`` 

  

``--license-model`` (string)


  License model information for this DB instance. 

   

  Valid values: ``license-included`` | ``bring-your-own-license`` | ``general-public-license`` 

  

``--iops`` (integer)


  The amount of Provisioned IOPS (input/output operations per second) to be initially allocated for the DB instance. 

   

  Constraints: Must be a multiple between 3 and 10 of the storage amount for the DB instance. Must also be an integer multiple of 1000. For example, if the size of your DB instance is 500 GB, then your ``Iops`` value can be 2000, 3000, 4000, or 5000. 

  

``--option-group-name`` (string)


  Indicates that the DB instance should be associated with the specified option group. 

   

  Permanent options, such as the TDE option for Oracle Advanced Security TDE, cannot be removed from an option group, and that option group cannot be removed from a DB instance once it is associated with a DB instance 

  

``--character-set-name`` (string)


  For supported engines, indicates that the DB instance should be associated with the specified CharacterSet. 

  

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



``--db-cluster-identifier`` (string)


  The identifier of the DB cluster that the instance will belong to.

   

  For information on creating a DB cluster, see  create-db-cluster .

   

  Type: monitoring-role-arn

  

``--storage-type`` (string)


  Specifies the storage type to be associated with the DB instance. 

   

  Valid values: ``standard | gp2 | io1`` 

   

  If you specify ``io1`` , you must also include a value for the ``Iops`` parameter. 

   

  Default: ``io1`` if the ``Iops`` parameter is specified; otherwise ``standard`` 

  

``--tde-credential-arn`` (string)


  The ARN from the Key Store with which to associate the instance for TDE encryption. 

  

``--tde-credential-password`` (string)


  The password for the given ARN from the Key Store in order to access the device. 

  

``--storage-encrypted`` | ``--no-storage-encrypted`` (boolean)


  Specifies whether the DB instance is encrypted. 

   

  Default: false 

  

``--kms-key-id`` (string)


  The KMS key identifier for an encrypted DB instance. 

   

  The KMS key identifier is the Amazon Resource Name (ARN) for the KMS encryption key. If you are creating a DB instance with the same AWS account that owns the KMS encryption key used to encrypt the new DB instance, then you can use the KMS key alias instead of the ARN for the KM encryption key.

   

  If the ``StorageEncrypted`` parameter is true, and you do not specify a value for the ``KmsKeyId`` parameter, then Amazon RDS will use your default encryption key. AWS KMS creates the default encryption key for your AWS account. Your AWS account has a different default encryption key for each AWS region.

  

``--copy-tags-to-snapshot`` | ``--no-copy-tags-to-snapshot`` (boolean)


  True to copy all tags from the DB instance to snapshots of the DB instance; otherwise false. The default is false.

  

``--monitoring-interval`` (integer)


  The interval, in seconds, between points when Enhanced Monitoring metrics are collected for the DB instance. To disable collecting Enhanced Monitoring metrics, specify 0. The default is 60.

   

  If ``MonitoringRoleArn`` is specified, then you must also set ``MonitoringInterval`` to a value other than 0.

   

  Valid Values: ``0, 1, 5, 10, 15, 30, 60`` 

  

``--monitoring-role-arn`` (string)


  The ARN for the IAM role that permits RDS to send enhanced monitoring metrics to CloudWatch Logs. For example, ``arn:aws:iam:123456789012:role/emaccess`` . For information on creating a monitoring role, go to `To create an IAM role for Amazon RDS Enhanced Monitoring`_ .

   

  If ``MonitoringInterval`` is set to a value other than 0, then you must supply a ``MonitoringRoleArn`` value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an Amazon RDS DB instance**

The following ``create-db-instance`` command launches a new Amazon RDS DB instance::

    aws rds create-db-instance --db-instance-identifier sg-cli-test \
    --allocated-storage 20 --db-instance-class db.m1.small --engine mysql \
    --master-username myawsuser --master-user-password myawsuser

In the preceding example, the DB instance is created with 20 Gb of standard storage and has a DB engine class of
db.m1.small. The master username and master password are provided.

This command outputs a JSON block that indicates that the DB instance was created::

    {
        "DBInstance": {
            "Engine": "mysql",
            "MultiAZ": false,
            "DBSecurityGroups": [
                {
                    "Status": "active",
                    "DBSecurityGroupName": "default"
                }
            ],
            "DBInstanceStatus": "creating",
            "DBParameterGroups": [
                {
                    "DBParameterGroupName": "default.mysql5.6",
                    "ParameterApplyStatus": "in-sync"
                }
            ],
            "MasterUsername": "myawsuser",
            "LicenseModel": "general-public-license",
            "OptionGroupMemberships": [
                {
                    "Status": "in-sync",
                    "OptionGroupName": "default:mysql-5-6"
                }
            ],
            "AutoMinorVersionUpgrade": true,
            "PreferredBackupWindow": "11:58-12:28",
            "VpcSecurityGroups": [],
            "PubliclyAccessible": true,
            "PreferredMaintenanceWindow": "sat:13:10-sat:13:40",
            "AllocatedStorage": 20,
            "EngineVersion": "5.6.13",
            "DBInstanceClass": "db.m1.small",
            "ReadReplicaDBInstanceIdentifiers": [],
            "BackupRetentionPeriod": 1,
            "DBInstanceIdentifier": "sg-cli-test",
            "PendingModifiedValues": {
                "MasterUserPassword": "****"
            }
        }
    }



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

    

    

  



.. _DB Instance Maintenance: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.DBMaintenance.html
.. _Adjusting the Preferred Maintenance Window: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/AdjustingTheMaintenanceWindow.html
.. _To create an IAM role for Amazon RDS Enhanced Monitoring: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Monitoring.html#USER_Monitoring.OS.IAMRole
.. _Regions and Availability Zones: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RegionsAndAvailabilityZones.html
.. _DB Instance Backups: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.BackingUpAndRestoringAmazonRDSInstances.html
