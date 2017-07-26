[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-elastic-load-balancers:


*******************************
describe-elastic-load-balancers
*******************************



===========
Description
===========



Describes a stack's Elastic Load Balancing instances.

 

.. note::

   

  This call accepts only one resource-identifying parameter.

   

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeElasticLoadBalancers>`_


========
Synopsis
========

::

    describe-elastic-load-balancers
  [--stack-id <value>]
  [--layer-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-id`` (string)


  A stack ID. The action describes the stack's Elastic Load Balancing instances.

  

``--layer-ids`` (list)


  A list of layer IDs. The action describes the Elastic Load Balancing instances for the specified layers.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a stack's elastic load balancers**

The following ``describe-elastic-load-balancers`` command describes a specified stack's load balancers.  ::

  aws opsworks --region us-west-2 describe-elastic-load-balancers --stack-id 6f4660e5-37a6-4e42-bfa0-1358ebd9c182

*Output*: This particular stack has one load balancer.

::

  {
    "ElasticLoadBalancers": [
        {
            "SubnetIds": [
                "subnet-60e4ea04",
                "subnet-66e1c110"
            ],
            "Ec2InstanceIds": [],
            "ElasticLoadBalancerName": "my-balancer",
            "Region": "us-west-2",
            "LayerId": "344973cb-bf2b-4cd0-8d93-51cd819bab04",
            "AvailabilityZones": [
                "us-west-2a",
                "us-west-2b"
            ],
            "VpcId": "vpc-b319f9d4",
            "StackId": "6f4660e5-37a6-4e42-bfa0-1358ebd9c182",
            "DnsName": "my-balancer-2094040179.us-west-2.elb.amazonaws.com"
        }
    ]
  }

**More Information**

For more information, see Apps_ in the *AWS OpsWorks User Guide*.

.. _Apps: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps.html


======
Output
======

ElasticLoadBalancers -> (list)

  

  A list of ``ElasticLoadBalancer`` objects that describe the specified Elastic Load Balancing instances.

  

  (structure)

    

    Describes an Elastic Load Balancing instance.

    

    ElasticLoadBalancerName -> (string)

      

      The Elastic Load Balancing instance's name.

      

      

    Region -> (string)

      

      The instance's AWS region.

      

      

    DnsName -> (string)

      

      The instance's public DNS name.

      

      

    StackId -> (string)

      

      The ID of the stack that the instance is associated with.

      

      

    LayerId -> (string)

      

      The ID of the layer that the instance is attached to.

      

      

    VpcId -> (string)

      

      The VPC ID.

      

      

    AvailabilityZones -> (list)

      

      A list of Availability Zones.

      

      (string)

        

        

      

    SubnetIds -> (list)

      

      A list of subnet IDs, if the stack is running in a VPC.

      

      (string)

        

        

      

    Ec2InstanceIds -> (list)

      

      A list of the EC2 instances that the Elastic Load Balancing instance is managing traffic for.

      

      (string)

        

        

      

    

  

