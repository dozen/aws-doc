[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-reserved-instances:


*************************
modify-reserved-instances
*************************



===========
Description
===========



Modifies the Availability Zone, instance count, instance type, or network platform (EC2-Classic or EC2-VPC) of your Reserved Instances. The Reserved Instances to be modified must be identical, except for Availability Zone, network platform, and instance type.

 

For more information, see `Modifying Reserved Instances`_ in the Amazon Elastic Compute Cloud User Guide.



========
Synopsis
========

::

    modify-reserved-instances
  [--client-token <value>]
  --reserved-instances-ids <value>
  --target-configurations <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--client-token`` (string)


  A unique, case-sensitive token you provide to ensure idempotency of your modification request. For more information, see `Ensuring Idempotency`_ .

  

``--reserved-instances-ids`` (list)


  The IDs of the Reserved Instances to modify.

  



Syntax::

  "string" "string" ...



``--target-configurations`` (list)


  The configuration settings for the Reserved Instances to modify.

  



Shorthand Syntax::

    AvailabilityZone=string,Platform=string,InstanceCount=integer,InstanceType=string ...




JSON Syntax::

  [
    {
      "AvailabilityZone": "string",
      "Platform": "string",
      "InstanceCount": integer,
      "InstanceType": "t1.micro"|"m1.small"|"m1.medium"|"m1.large"|"m1.xlarge"|"m3.medium"|"m3.large"|"m3.xlarge"|"m3.2xlarge"|"m4.large"|"m4.xlarge"|"m4.2xlarge"|"m4.4xlarge"|"m4.10xlarge"|"t2.nano"|"t2.micro"|"t2.small"|"t2.medium"|"t2.large"|"m2.xlarge"|"m2.2xlarge"|"m2.4xlarge"|"cr1.8xlarge"|"i2.xlarge"|"i2.2xlarge"|"i2.4xlarge"|"i2.8xlarge"|"hi1.4xlarge"|"hs1.8xlarge"|"c1.medium"|"c1.xlarge"|"c3.large"|"c3.xlarge"|"c3.2xlarge"|"c3.4xlarge"|"c3.8xlarge"|"c4.large"|"c4.xlarge"|"c4.2xlarge"|"c4.4xlarge"|"c4.8xlarge"|"cc1.4xlarge"|"cc2.8xlarge"|"g2.2xlarge"|"cg1.4xlarge"|"r3.large"|"r3.xlarge"|"r3.2xlarge"|"r3.4xlarge"|"r3.8xlarge"|"d2.xlarge"|"d2.2xlarge"|"d2.4xlarge"|"d2.8xlarge"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To modify Reserved Instances**

This example command moves a Reserved Instance to another Availability Zone in the same region.

Command::

  aws ec2 modify-reserved-instances --reserved-instances-ids b847fa93-e282-4f55-b59a-1342f5bd7c02 --target-configurations AvailabilityZone=us-west-1c,Platform=EC2-Classic,InstanceCount=10

Output::

  {
    "ReservedInstancesModificationId": "rimod-d3ed4335-b1d3-4de6-ab31-0f13aaf46687"
  }


**To modify the network platform of Reserved Instances**

This example command converts EC2-Classic Reserved Instances to EC2-VPC.

Command::

  aws ec2 modify-reserved-instances --reserved-instances-ids f127bd27-edb7-44c9-a0eb-0d7e09259af0 --target-configurations AvailabilityZone=us-west-1c,Platform=EC2-VPC,InstanceCount=5

Output::

  {
    "ReservedInstancesModificationId": "rimod-82fa9020-668f-4fb6-945d-61537009d291"
  }

For more information, see `Modifying Your Reserved Instances`_ in the *Amazon EC2 User Guide*.

**To modify the instance types of Reserved Instances**

This example command modifies a Reserved Instance that has 10 m1.small Linux/UNIX instances in us-west-1c so that 8
m1.small instances become 2 m1.large instances, and the remaining 2 m1.small become 1 m1.medium instance in the same
Availability Zone.  Command::

  aws ec2 modify-reserved-instances --reserved-instances-ids 1ba8e2e3-3556-4264-949e-63ee671405a9 --target-configurations AvailabilityZone=us-west-1c,Platform=EC2-Classic,InstanceCount=2,InstanceType=m1.large AvailabilityZone=us-west-1c,Platform=EC2-Classic,InstanceCount=1,InstanceType=m1.medium

Output::

  {
      "ReservedInstancesModificationId": "rimod-acc5f240-080d-4717-b3e3-1c6b11fa00b6"
  }

For more information, see `Changing the Instance Type of Your Reservations`_ in the *Amazon EC2 User Guide*.

.. _`Changing the Instance Type of Your Reservations`: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-modification-instancemove.html
.. _`Modifying Your Reserved Instances`: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-modifying.html



======
Output
======

ReservedInstancesModificationId -> (string)

  

  The ID for the modification.

  

  



.. _Ensuring Idempotency: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html
.. _Modifying Reserved Instances: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-modifying.html
