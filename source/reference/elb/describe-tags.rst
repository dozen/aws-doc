[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb describe-tags:


*************
describe-tags
*************



===========
Description
===========



Describes the tags associated with the specified load balancers.



========
Synopsis
========

::

    describe-tags
  --load-balancer-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-names`` (list)


  The names of the load balancers.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

          

          

        

      

    

  

