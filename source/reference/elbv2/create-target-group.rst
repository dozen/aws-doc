[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 create-target-group:


*******************
create-target-group
*******************



===========
Description
===========



Creates a target group.

 

To register targets with the target group, use  register-targets . To update the health check settings for the target group, use  modify-target-group . To monitor the health of targets in the target group, use  describe-target-health .

 

To route traffic to the targets in a target group, specify the target group in an action using  create-listener or  create-rule .

 

To delete a target group, use  delete-target-group .

 

For more information, see `Target Groups for Your Application Load Balancers <http://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html>`_ in the *Application Load Balancers Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/CreateTargetGroup>`_


========
Synopsis
========

::

    create-target-group
  --name <value>
  --protocol <value>
  --port <value>
  --vpc-id <value>
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

``--name`` (string)


  The name of the target group.

   

  This name must be unique per region per account, can have a maximum of 32 characters, must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen.

  

``--protocol`` (string)


  The protocol to use for routing traffic to the targets.

  

  Possible values:

  
  *   ``HTTP``

  
  *   ``HTTPS``

  

  

``--port`` (integer)


  The port on which the targets receive traffic. This port is used unless you specify a port override when registering the target.

  

``--vpc-id`` (string)


  The identifier of the virtual private cloud (VPC).

  

``--health-check-protocol`` (string)


  The protocol the load balancer uses when performing health checks on targets. The default is the HTTP protocol.

  

  Possible values:

  
  *   ``HTTP``

  
  *   ``HTTPS``

  

  

``--health-check-port`` (string)


  The port the load balancer uses when performing health checks on targets. The default is ``traffic-port`` , which indicates the port on which each target receives traffic from the load balancer.

  

``--health-check-path`` (string)


  The ping path that is the destination on the targets for health checks. The default is /.

  

``--health-check-interval-seconds`` (integer)


  The approximate amount of time, in seconds, between health checks of an individual target. The default is 30 seconds.

  

``--health-check-timeout-seconds`` (integer)


  The amount of time, in seconds, during which no response from a target means a failed health check. The default is 5 seconds.

  

``--healthy-threshold-count`` (integer)


  The number of consecutive health checks successes required before considering an unhealthy target healthy. The default is 5.

  

``--unhealthy-threshold-count`` (integer)


  The number of consecutive health check failures required before considering a target unhealthy. The default is 2.

  

``--matcher`` (structure)


  The HTTP codes to use when checking for a successful response from a target. The default is 200.

  



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

**To create a target group**

This example creates a target group that you can use to route traffic to targets using HTTP on port 80. This target group uses the default health check configuration.

Command::

  aws elbv2 create-target-group --name my-targets --protocol HTTP --port 80 --vpc-id vpc-3ac0fb5f

Output::

  {
    "TargetGroups": [
        {
            "HealthCheckPath": "/",
            "HealthCheckIntervalSeconds": 30,
            "VpcId": "vpc-3ac0fb5f",
            "Protocol": "HTTP",
            "HealthCheckTimeoutSeconds": 5,
            "HealthCheckProtocol": "HTTP",
            "UnhealthyThresholdCount": 2,
            "HealthyThresholdCount": 5,
            "TargetGroupArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067",
            "Matcher": {
                "HttpCode": "200"
            },
            "HealthCheckPort": "traffic-port",
            "Port": 80,
            "TargetGroupName": "my-targets"
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

        

        

      

    

  

