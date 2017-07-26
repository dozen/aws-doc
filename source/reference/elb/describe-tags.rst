[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb describe-tags:


*************
describe-tags
*************



===========
Description
===========



Describes the tags associated with the specified load balancers.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/DescribeTags>`_


========
Synopsis
========

::

    describe-tags
  --load-balancer-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-names`` (list)


  The names of the load balancers.

  



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

  aws elb describe-tags --load-balancer-name my-load-balancer

Output::

  {
    "TagDescriptions": [
        {
            "Tags": [                
                {
                    "Value": "lima", 
                    "Key": "project"
                },
                {
                    "Value": "digital-media",
                    "Key": "department"
                }
            ], 
            "LoadBalancerName": "my-load-balancer"
        }
    ]
  }



======
Output
======

TagDescriptions -> (list)

  

  Information about the tags.

  

  (structure)

    

    The tags associated with a load balancer.

    

    LoadBalancerName -> (string)

      

      The name of the load balancer.

      

      

    Tags -> (list)

      

      The tags.

      

      (structure)

        

        Information about a tag.

        

        Key -> (string)

          

          The key of the tag.

          

          

        Value -> (string)

          

          The value of the tag.

          

          

        

      

    

  

