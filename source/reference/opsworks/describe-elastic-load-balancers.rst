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

   

  You must specify at least one of the parameters.

   

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-elastic-load-balancers
  [--stack-id <value>]
  [--layer-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe a stack's elastic load balancers**

The following ``describe-elastic-load-balancers`` command describes a specified stack's load balancers.  ::

  aws opsworks --region us-west-1 describe-elastic-load-balancers --stack-id d72553d4-8727-448c-9b00-f024f0ba1b06

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: This particular stack has one app.

::

  {
    "Apps": [
      {
        "StackId": "38ee91e2-abdc-4208-a107-0b7168b3cc7a",
        "AppSource": {
          "Url": "https://s3-us-west-2.amazonaws.com/opsworks-tomcat/simplejsp.zip",
          "Type": "archive"
        },
        "Name": "SimpleJSP",
        "EnableSsl": false,
        "SslConfiguration": {},
        "AppId": "da1decc1-0dff-43ea-ad7c-bb667cd87c8b",
        "Attributes": {
          "RailsEnv": null,
          "AutoBundleOnDeploy": "true",
          "DocumentRoot": "ROOT"
        },
        "Shortname": "simplejsp",
        "Type": "other",
        "CreatedAt": "2013-08-01T21:46:54+00:00"
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

        

        

      

    

  



.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
