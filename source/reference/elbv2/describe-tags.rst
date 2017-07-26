[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 describe-tags:


*************
describe-tags
*************



===========
Description
===========



Describes the tags for the specified resources. You can describe the tags for one or more Application Load Balancers and target groups.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/DescribeTags>`_


========
Synopsis
========

::

    describe-tags
  --resource-arns <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arns`` (list)


  The Amazon Resource Names (ARN) of the resources.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the tags assigned to a load balancer**

This example describes the tags assigned to the specified load balancer.

Command::

  aws elbv2 describe-tags --resource-arns arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188
  
Output::

  {
    "TagDescriptions": [
        {
            "ResourceArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188",
            "Tags": [
                {
                    "Value": "lima",
                    "Key": "project"
                },
                {
                    "Value": "digital-media",
                    "Key": "department"
                }
            ]
        }
    ]
  }


======
Output
======

TagDescriptions -> (list)

  

  Information about the tags.

  

  (structure)

    

    The tags associated with a resource.

    

    ResourceArn -> (string)

      

      The Amazon Resource Name (ARN) of the resource.

      

      

    Tags -> (list)

      

      Information about the tags.

      

      (structure)

        

        Information about a tag.

        

        Key -> (string)

          

          The key of the tag.

          

          

        Value -> (string)

          

          The value of the tag.

          

          

        

      

    

  

