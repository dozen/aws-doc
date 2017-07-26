[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms modify-replication-instance:


***************************
modify-replication-instance
***************************



===========
Description
===========



Modifies the replication instance to apply new settings. You can change one or more parameters by specifying these parameters and the new values in the request.

 

Some settings are applied during the maintenance window.

 





See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/ModifyReplicationInstance>`_


========
Synopsis
========

::

    modify-replication-instance
  --replication-instance-arn <value>
  [--allocated-storage <value>]
  [--apply-immediately | --no-apply-immediately]
  [--replication-instance-class <value>]
  [--vpc-security-group-ids <value>]
  [--preferred-maintenance-window <value>]
  [--multi-az | --no-multi-az]
  [--engine-version <value>]
  [--allow-major-version-upgrade | --no-allow-major-version-upgrade]
  [--auto-minor-version-upgrade | --no-auto-minor-version-upgrade]
  [--replication-instance-identifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-instance-arn`` (string)


  The Amazon Resource Name (ARN) of the replication instance.

  

``--allocated-storage`` (integer)


  The amount of storage (in gigabytes) to be allocated for the replication instance.

  

``--apply-immediately`` | ``--no-apply-immediately`` (boolean)


  Indicates whether the changes should be applied immediately or during the next maintenance window.

  

``--replication-instance-class`` (string)


  The compute and memory capacity of the replication instance.

   

  Valid Values: ``dms.t2.micro | dms.t2.small | dms.t2.medium | dms.t2.large | dms.c4.large | dms.c4.xlarge | dms.c4.2xlarge | dms.c4.4xlarge``  

  

``--vpc-security-group-ids`` (list)


  Specifies the VPC security group to be used with the replication instance. The VPC security group must work with the VPC containing the replication instance. 

  



Syntax::

  "string" "string" ...



``--preferred-maintenance-window`` (string)


  The weekly time range (in UTC) during which system maintenance can occur, which might result in an outage. Changing this parameter does not result in an outage, except in the following situation, and the change is asynchronously applied as soon as possible. If moving this window to the current time, there must be at least 30 minutes between the current time and end of the window to ensure pending changes are applied.

   

  Default: Uses existing setting

   

  Format: ddd:hh24:mi-ddd:hh24:mi

   

  Valid Days: Mon | Tue | Wed | Thu | Fri | Sat | Sun

   

  Constraints: Must be at least 30 minutes

  

``--multi-az`` | ``--no-multi-az`` (boolean)


  Specifies if the replication instance is a Multi-AZ deployment. You cannot set the ``AvailabilityZone`` parameter if the Multi-AZ parameter is set to ``true`` . 

  

``--engine-version`` (string)


  The engine version number of the replication instance.

  

``--allow-major-version-upgrade`` | ``--no-allow-major-version-upgrade`` (boolean)


  Indicates that major version upgrades are allowed. Changing this parameter does not result in an outage and the change is asynchronously applied as soon as possible.

   

  Constraints: This parameter must be set to true when specifying a value for the ``EngineVersion`` parameter that is a different major version than the replication instance's current version.

  

``--auto-minor-version-upgrade`` | ``--no-auto-minor-version-upgrade`` (boolean)


  Indicates that minor version upgrades will be applied automatically to the replication instance during the maintenance window. Changing this parameter does not result in an outage except in the following case and the change is asynchronously applied as soon as possible. An outage will result if this parameter is set to ``true`` during the maintenance window, and a newer minor version is available, and AWS DMS has enabled auto patching for that engine version. 

  

``--replication-instance-identifier`` (string)


  The replication instance identifier. This parameter is stored as a lowercase string.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ReplicationInstance -> (structure)

  

  The modified replication instance.

  

  ReplicationInstanceIdentifier -> (string)

    

    The replication instance identifier. This parameter is stored as a lowercase string.

     

    Constraints:

     

     
    * Must contain from 1 to 63 alphanumeric characters or hyphens. 
     
    * First character must be a letter. 
     
    * Cannot end with a hyphen or contain two consecutive hyphens. 
     

     

    Example: ``myrepinstance``  

    

    

  ReplicationInstanceClass -> (string)

    

    The compute and memory capacity of the replication instance.

     

    Valid Values: ``dms.t2.micro | dms.t2.small | dms.t2.medium | dms.t2.large | dms.c4.large | dms.c4.xlarge | dms.c4.2xlarge | dms.c4.4xlarge``  

    

    

  ReplicationInstanceStatus -> (string)

    

    The status of the replication instance.

    

    

  AllocatedStorage -> (integer)

    

    The amount of storage (in gigabytes) that is allocated for the replication instance.

    

    

  InstanceCreateTime -> (timestamp)

    

    The time the replication instance was created.

    

    

  VpcSecurityGroups -> (list)

    

    The VPC security group for the instance.

    

    (structure)

      

      

      

      VpcSecurityGroupId -> (string)

        

        The VPC security group Id.

        

        

      Status -> (string)

        

        The status of the VPC security group.

        

        

      

    

  AvailabilityZone -> (string)

    

    The Availability Zone for the instance.

    

    

  ReplicationSubnetGroup -> (structure)

    

    The subnet group for the replication instance.

    

    ReplicationSubnetGroupIdentifier -> (string)

      

      The identifier of the replication instance subnet group.

      

      

    ReplicationSubnetGroupDescription -> (string)

      

      The description of the replication subnet group.

      

      

    VpcId -> (string)

      

      The ID of the VPC.

      

      

    SubnetGroupStatus -> (string)

      

      The status of the subnet group.

      

      

    Subnets -> (list)

      

      The subnets that are in the subnet group.

      

      (structure)

        

        

        

        SubnetIdentifier -> (string)

          

          The subnet identifier.

          

          

        SubnetAvailabilityZone -> (structure)

          

          The Availability Zone of the subnet.

          

          Name -> (string)

            

            The name of the availability zone.

            

            

          

        SubnetStatus -> (string)

          

          The status of the subnet.

          

          

        

      

    

  PreferredMaintenanceWindow -> (string)

    

    The maintenance window times for the replication instance.

    

    

  PendingModifiedValues -> (structure)

    

    The pending modification values.

    

    ReplicationInstanceClass -> (string)

      

      The compute and memory capacity of the replication instance.

       

      Valid Values: ``dms.t2.micro | dms.t2.small | dms.t2.medium | dms.t2.large | dms.c4.large | dms.c4.xlarge | dms.c4.2xlarge | dms.c4.4xlarge``  

      

      

    AllocatedStorage -> (integer)

      

      The amount of storage (in gigabytes) that is allocated for the replication instance.

      

      

    MultiAZ -> (boolean)

      

      Specifies if the replication instance is a Multi-AZ deployment. You cannot set the ``AvailabilityZone`` parameter if the Multi-AZ parameter is set to ``true`` . 

      

      

    EngineVersion -> (string)

      

      The engine version number of the replication instance.

      

      

    

  MultiAZ -> (boolean)

    

    Specifies if the replication instance is a Multi-AZ deployment. You cannot set the ``AvailabilityZone`` parameter if the Multi-AZ parameter is set to ``true`` . 

    

    

  EngineVersion -> (string)

    

    The engine version number of the replication instance.

    

    

  AutoMinorVersionUpgrade -> (boolean)

    

    apply-immediately value indicating if minor version upgrades will be automatically applied to the instance.

    

    

  KmsKeyId -> (string)

    

    The KMS key identifier that is used to encrypt the content on the replication instance. If you do not specify a value for the KmsKeyId parameter, then AWS DMS will use your default encryption key. AWS KMS creates the default encryption key for your AWS account. Your AWS account has a different default encryption key for each AWS region.

    

    

  ReplicationInstanceArn -> (string)

    

    The Amazon Resource Name (ARN) of the replication instance.

    

    

  ReplicationInstancePublicIpAddress -> (string)

    

    The public IP address of the replication instance.

    

    

  ReplicationInstancePrivateIpAddress -> (string)

    

    The private IP address of the replication instance.

    

    

  ReplicationInstancePublicIpAddresses -> (list)

    

    The public IP address of the replication instance.

    

    (string)

      

      

    

  ReplicationInstancePrivateIpAddresses -> (list)

    

    The private IP address of the replication instance.

    

    (string)

      

      

    

  PubliclyAccessible -> (boolean)

    

    Specifies the accessibility options for the replication instance. A value of ``true`` represents an instance with a public IP address. A value of ``false`` represents an instance with a private IP address. The default value is ``true`` . 

    

    

  SecondaryAvailabilityZone -> (string)

    

    The availability zone of the standby replication instance in a Multi-AZ deployment.

    

    

  

