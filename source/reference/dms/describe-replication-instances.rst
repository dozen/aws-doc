[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms describe-replication-instances:


******************************
describe-replication-instances
******************************



===========
Description
===========



Returns information about replication instances for your account in the current region.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DescribeReplicationInstances>`_


========
Synopsis
========

::

    describe-replication-instances
  [--filters <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  Filters applied to the describe action.

   

  Valid filter names: replication-instance-arn | replication-instance-id | replication-instance-class | engine-version

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--marker`` (string)


  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

ReplicationInstances -> (list)

  

  The replication instances described.

  

  (structure)

    

    

    

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

      

      

    

  

