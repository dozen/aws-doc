[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 modify-target-group:


*******************
modify-target-group
*******************



===========
Description
===========



Modifies the health checks used when evaluating the health state of the targets in the specified target group.

 

To monitor the health of the targets, use  describe-target-health .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/ModifyTargetGroup>`_


========
Synopsis
========

::

    modify-target-group
  --target-group-arn <value>
  [--health-check-protocol <value>]
  [--health-check-port <value>]
  [--health-check-path <value>]
  [--health-check-interval-seconds <value>]
  [--health-check-timeout-seconds <value>]
  [--healthy-threshold-count <value>]
  [--unhealthy-threshold-count <value>]
  [--matcher <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--target-group-arn`` (string)


  The Amazon Resource Name (ARN) of the target group.

  

``--health-check-protocol`` (string)


  The protocol to use to connect with the target.

  

  Possible values:

  
  *   ``HTTP``

  
  *   ``HTTPS``

  

  

``--health-check-port`` (string)


  The port to use to connect with the target.

  

``--health-check-path`` (string)


  The ping path that is the destination for the health check request.

  

``--health-check-interval-seconds`` (integer)


  The approximate amount of time, in seconds, between health checks of an individual target.

  

``--health-check-timeout-seconds`` (integer)


  The amount of time, in seconds, during which no response means a failed health check.

  

``--healthy-threshold-count`` (integer)


  The number of consecutive health checks successes required before considering an unhealthy target healthy.

  

``--unhealthy-threshold-count`` (integer)


  The number of consecutive health check failures required before considering the target unhealthy.

  

``--matcher`` (structure)


  The HTTP codes to use when checking for a successful response from a target.

  



Shorthand Syntax::

    HttpCode=string




JSON Syntax::

  {
    "HttpCode": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To modify the health check configuration for a target group**

This example changes the configuration of the health checks used to evaluate the health of the targets for the specified target group.

Command::

  aws elbv2 modify-target-group --target-group-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-https-targets/2453ed029918f21f --health-check-protocol HTTPS --health-check-port 443
  
Output::

  {
    "TargetGroups": [
        {
            "HealthCheckIntervalSeconds": 30,
            "VpcId": "vpc-3ac0fb5f",
            "Protocol": "HTTPS",
            "HealthCheckTimeoutSeconds": 5,
            "HealthCheckProtocol": "HTTPS",
            "LoadBalancerArns": [
                "arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188"
            ],
            "UnhealthyThresholdCount": 2,
            "HealthyThresholdCount": 5,
            "TargetGroupArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-https-targets/2453ed029918f21f",
            "Matcher": {
                "HttpCode": "200"
            },
            "HealthCheckPort": "443",
            "Port": 443,
            "TargetGroupName": "my-https-targets"
        }
    ]
  }


======
Output
======

TargetGroups -> (list)

  

  Information about the target group.

  

  (structure)

    

    Information about a target group.

    

    TargetGroupArn -> (string)

      

      The Amazon Resource Name (ARN) of the target group.

      

      

    TargetGroupName -> (string)

      

      The name of the target group.

      

      

    Protocol -> (string)

      

      The protocol to use for routing traffic to the targets.

      

      

    Port -> (integer)

      

      The port on which the targets are listening.

      

      

    VpcId -> (string)

      

      The ID of the VPC for the targets.

      

      

    HealthCheckProtocol -> (string)

      

      The protocol to use to connect with the target.

      

      

    HealthCheckPort -> (string)

      

      The port to use to connect with the target.

      

      

    HealthCheckIntervalSeconds -> (integer)

      

      The approximate amount of time, in seconds, between health checks of an individual target.

      

      

    HealthCheckTimeoutSeconds -> (integer)

      

      The amount of time, in seconds, during which no response means a failed health check.

      

      

    HealthyThresholdCount -> (integer)

      

      The number of consecutive health checks successes required before considering an unhealthy target healthy.

      

      

    UnhealthyThresholdCount -> (integer)

      

      The number of consecutive health check failures required before considering the target unhealthy.

      

      

    HealthCheckPath -> (string)

      

      The destination for the health check request.

      

      

    Matcher -> (structure)

      

      The HTTP codes to use when checking for a successful response from a target.

      

      HttpCode -> (string)

        

        The HTTP codes. You can specify values between 200 and 499. The default value is 200. You can specify multiple values (for example, "200,202") or a range of values (for example, "200-299").

        

        

      

    LoadBalancerArns -> (list)

      

      The Amazon Resource Names (ARN) of the load balancers that route traffic to this target group.

      

      (string)

        

        

      

    

  

