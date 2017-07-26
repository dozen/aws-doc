[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-account-attributes:


***************************
describe-account-attributes
***************************



===========
Description
===========



Describes attributes of your AWS account. The following are the supported account attributes:

 

 
* ``supported-platforms`` : Indicates whether your account can launch instances into EC2-Classic and EC2-VPC, or only into EC2-VPC. 
 
* ``default-vpc`` : The ID of the default VPC for your account, or ``none`` . 
 
* ``max-instances`` : The maximum number of On-Demand instances that you can run. 
 
* ``vpc-max-security-groups-per-interface`` : The maximum number of security groups that you can assign to a network interface. 
 
* ``max-elastic-ips`` : The maximum number of Elastic IP addresses that you can allocate for use with EC2-Classic.  
 
* ``vpc-max-elastic-ips`` : The maximum number of Elastic IP addresses that you can allocate for use with EC2-VPC. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeAccountAttributes>`_


========
Synopsis
========

::

    describe-account-attributes
  [--attribute-names <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute-names`` (list)


  One or more account attribute names.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    supported-platforms
    default-vpc





``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe all the attributes for your AWS account**

This example describes the attributes for your AWS account.

Command::

  aws ec2 describe-account-attributes

Output::

  {
      "AccountAttributes": [
          {
              "AttributeName": "vpc-max-security-groups-per-interface",
              "AttributeValues": [
                  {
                      "AttributeValue": "5"
                  }
              ]
          },
          {
              "AttributeName": "max-instances",
              "AttributeValues": [
                  {
                      "AttributeValue": "20"
                  }
              ]
          },
          {
              "AttributeName": "supported-platforms",
              "AttributeValues": [
                  {
                      "AttributeValue": "EC2"
                  },
                  {
                      "AttributeValue": "VPC"
                  }
              ]
          },
          {
              "AttributeName": "default-vpc",
              "AttributeValues": [
                  {
                      "AttributeValue": "none"
                  }
              ]
          },
          {
              "AttributeName": "max-elastic-ips",
              "AttributeValues": [
                  {
                      "AttributeValue": "5"
                  }
              ]
          },
          {
              "AttributeName": "vpc-max-elastic-ips",
              "AttributeValues": [
                  {
                      "AttributeValue": "5"
                  }
              ]
          }
      ]
  }

**To describe a single attribute for your AWS account**

This example describes the ``supported-platforms`` attribute for your AWS account.

Command::

  aws ec2 describe-account-attributes --attribute-names supported-platforms

Output::

  {
      "AccountAttributes": [
          {
              "AttributeName": "supported-platforms",
              "AttributeValues": [
                  {
                      "AttributeValue": "EC2"
                  },
                  {
                      "AttributeValue": "VPC"
                  }
              ]
          }
      ]
  }



======
Output
======

AccountAttributes -> (list)

  

  Information about one or more account attributes.

  

  (structure)

    

    Describes an account attribute.

    

    AttributeName -> (string)

      

      The name of the account attribute.

      

      

    AttributeValues -> (list)

      

      One or more values for the account attribute.

      

      (structure)

        

        Describes a value of an account attribute.

        

        AttributeValue -> (string)

          

          The value of the attribute.

          

          

        

      

    

  

