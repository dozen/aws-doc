[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms create-replication-instance:


***************************
create-replication-instance
***************************



===========
Description
===========



Creates the replication instance using the specified parameters.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/CreateReplicationInstance>`_


========
Synopsis
========

::

    create-replication-instance
  --replication-instance-identifier <value>
  [--allocated-storage <value>]
  --replication-instance-class <value>
  [--vpc-security-group-ids <value>]
  [--availability-zone <value>]
  [--replication-subnet-group-identifier <value>]
  [--preferred-maintenance-window <value>]
  [--multi-az | --no-multi-az]
  [--engine-version <value>]
  [--auto-minor-version-upgrade | --no-auto-minor-version-upgrade]
  [--tags <value>]
  [--kms-key-id <value>]
  [--publicly-accessible | --no-publicly-accessible]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-instance-identifier`` (string)


  The replication instance identifier. This parameter is stored as a lowercase string.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens. 
   
  * First character must be a letter. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   

   

  Example: ``myrepinstance``  

  

``--allocated-storage`` (integer)


  The amount of storage (in gigabytes) to be initially allocated for the replication instance.

  

``--replication-instance-class`` (string)


  The compute and memory capacity of the replication instance as specified by the replication instance class.

   

  Valid Values: ``dms.t2.micro | dms.t2.small | dms.t2.medium | dms.t2.large | dms.c4.large | dms.c4.xlarge | dms.c4.2xlarge | dms.c4.4xlarge``  

  

``--vpc-security-group-ids`` (list)


  Specifies the VPC security group to be used with the replication instance. The VPC security group must work with the VPC containing the replication instance. 

  



Syntax::

  "string" "string" ...



``--availability-zone`` (string)


  The EC2 Availability Zone that the replication instance will be created in.

   

  Default: A random, system-chosen Availability Zone in the endpoint's region.

   

  Example: ``us-east-1d``  

  

``--replication-subnet-group-identifier`` (string)


  A subnet group to associate with the replication instance.

  

``--preferred-maintenance-window`` (string)


  The weekly time range during which system maintenance can occur, in Universal Coordinated Time (UTC).

   

  Format: ``ddd:hh24:mi-ddd:hh24:mi``  

   

  Default: A 30-minute window selected at random from an 8-hour block of time per region, occurring on a random day of the week.

   

  Valid Days: Mon, Tue, Wed, Thu, Fri, Sat, Sun

   

  Constraints: Minimum 30-minute window.

  

``--multi-az`` | ``--no-multi-az`` (boolean)


  Specifies if the replication instance is a Multi-AZ deployment. You cannot set the ``AvailabilityZone`` parameter if the Multi-AZ parameter is set to ``true`` . 

  

``--engine-version`` (string)


  The engine version number of the replication instance.

  

``--auto-minor-version-upgrade`` | ``--no-auto-minor-version-upgrade`` (boolean)


  Indicates that minor engine upgrades will be applied automatically to the replication instance during the maintenance window.

   

  Default: ``true``  

  

``--tags`` (list)


  Tags to be associated with the replication instance.

  



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


  The KMS key identifier that will be used to encrypt the content on the replication instance. If you do not specify a value for the KmsKeyId parameter, then AWS DMS will use your default encryption key. AWS KMS creates the default encryption key for your AWS account. Your AWS account has a different default encryption key for each AWS region.

  

``--publicly-accessible`` | ``--no-publicly-accessible`` (boolean)


  Specifies the accessibility options for the replication instance. A value of ``true`` represents an instance with a public IP address. A value of ``false`` represents an instance with a private IP address. The default value is ``true`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command creates a replication instance named ``my-replication-db`` with 5GB of storage::

  aws dms create-replication-instance --replication-instance-identifier my-replication-db --replication-instance-class dms.t2.micro --allocated-storage 5

Output::

  {
    "ReplicationInstance": {
      "PubliclyAccessible": true,
      "ReplicationInstanceArn": "arn:aws:dms:us-east-1:123456789012:rep:6UTDJGBOUS3VI3SUWA66XFJCJQ ",
      "ReplicationInstanceClass": "dms.t2.micro",
      "ReplicationSubnetGroup": {
        "ReplicationSubnetGroupDescription": "default",
        "Subnets": [{
          "SubnetStatus": "Active",
          "SubnetIdentifier": "subnet-f6dd91af",
          "SubnetAvailabilityZone": {
            "Name": "us-east-1d"
          }
        }, {
          "SubnetStatus": "Active",
          "SubnetIdentifier": "subnet-3605751d",
          "SubnetAvailabilityZone": {
            "Name": "us-east-1b"
          }
        }, {
          "SubnetStatus": "Active",
          "SubnetIdentifier": "subnet-c2daefb5",
          "SubnetAvailabilityZone": {
            "Name": "us-east-1c"
          }
        }, {
          "SubnetStatus": "Active",
          "SubnetIdentifier": "subnet-85e90cb8",
          "SubnetAvailabilityZone": {
            "Name": "us-east-1e"
          }
        }],
        "VpcId": "vpc-6741a603",
        "SubnetGroupStatus": "Complete",
        "ReplicationSubnetGroupIdentifier": "default"
      },
      "AutoMinorVersionUpgrade": true,
      "ReplicationInstanceStatus": "creating",
      "KmsKeyId": "arn:aws:kms:us-east-1:123456789012:key/4c1731d6-5435-ed4d-be13-d53411a7cfbd",
      "AllocatedStorage": 5,
      "EngineVersion": "1.5.0",
      "ReplicationInstanceIdentifier": "test-rep-1",
      "PreferredMaintenanceWindow": "sun:06:00-sun:14:00",
      "PendingModifiedValues": {}
    }
  }


======
Output
======

ReplicationInstance -> (structure)

  

  The replication instance that was created.

  

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

    

    Boolean value indicating if minor version upgrades will be automatically applied to the instance.

    

    

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

    

    

  

