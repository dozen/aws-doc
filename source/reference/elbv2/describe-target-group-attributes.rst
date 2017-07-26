[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 describe-target-group-attributes:


********************************
describe-target-group-attributes
********************************



===========
Description
===========



Describes the attributes for the specified target group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/DescribeTargetGroupAttributes>`_


========
Synopsis
========

::

    describe-target-group-attributes
  --target-group-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--target-group-arn`` (string)


  The Amazon Resource Name (ARN) of the target group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe target group attributes**

This example describes the attributes of the specified target group.

Command::

  aws elbv2 describe-target-group-attributes --target-group-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067

Output::

  {
    "Attributes": [
        {
            "Value": "false",
            "Key": "stickiness.enabled"
        },
        {
            "Value": "300",
            "Key": "deregistration_delay.timeout_seconds"
        },
        {
            "Value": "lb_cookie",
            "Key": "stickiness.type"
        },
        {
            "Value": "86400",
            "Key": "stickiness.lb_cookie.duration_seconds"
        }
    ]
  }


======
Output
======

Attributes -> (list)

  

  Information about the target group attributes

  

  (structure)

    

    Information about a target group attribute.

    

    Key -> (string)

      

      The name of the attribute.

       

       
      * ``deregistration_delay.timeout_seconds`` - The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from ``draining`` to ``unused`` . The range is 0-3600 seconds. The default value is 300 seconds. 
       
      * ``stickiness.enabled`` - Indicates whether sticky sessions are enabled. The value is ``true`` or ``false`` . 
       
      * ``stickiness.type`` - The type of sticky sessions. The possible value is ``lb_cookie`` . 
       
      * ``stickiness.lb_cookie.duration_seconds`` - The time period, in seconds, during which requests from a client should be routed to the same target. After this time period expires, the load balancer-generated cookie is considered stale. The range is 1 second to 1 week (604800 seconds). The default value is 1 day (86400 seconds). 
       

      

      

    Value -> (string)

      

      The value of the attribute.

      

      

    

  

