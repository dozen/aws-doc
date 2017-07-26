[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-elastic-ips:


********************
describe-elastic-ips
********************



===========
Description
===========



Describes `Elastic IP addresses <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html>`_ .

 

.. note::

   

  This call accepts only one resource-identifying parameter.

   

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeElasticIps>`_


========
Synopsis
========

::

    describe-elastic-ips
  [--instance-id <value>]
  [--stack-id <value>]
  [--ips <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The instance ID. If you include this parameter, ``describe-elastic-ips`` returns a description of the Elastic IP addresses associated with the specified instance.

  

``--stack-id`` (string)


  A stack ID. If you include this parameter, ``describe-elastic-ips`` returns a description of the Elastic IP addresses that are registered with the specified stack.

  

``--ips`` (list)


  An array of Elastic IP addresses to be described. If you include this parameter, ``describe-elastic-ips`` returns a description of the specified Elastic IP addresses. Otherwise, it returns a description of every Elastic IP address.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe Elastic IP instances**

The following ``describe-elastic-ips`` commmand describes the Elastic IP addresses in a specified instance. ::

  aws opsworks --region us-east-1 describe-elastic-ips --instance-id b62f3e04-e9eb-436c-a91f-d9e9a396b7b0

*Output*::

  {
    "ElasticIps": [
        {
            "Ip": "192.0.2.0",
            "Domain": "standard",
            "Region": "us-west-2"
        }
    ]
  }

**More Information**

For more information, see Instances_ in the *AWS OpsWorks User Guide*.

.. _Instances: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances.html



======
Output
======

ElasticIps -> (list)

  

  An ``ElasticIps`` object that describes the specified Elastic IP addresses.

  

  (structure)

    

    Describes an Elastic IP address.

    

    Ip -> (string)

      

      The IP address.

      

      

    Name -> (string)

      

      The name.

      

      

    Domain -> (string)

      

      The domain.

      

      

    Region -> (string)

      

      The AWS region. For more information, see `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html>`_ .

      

      

    InstanceId -> (string)

      

      The ID of the instance that the address is attached to.

      

      

    

  

