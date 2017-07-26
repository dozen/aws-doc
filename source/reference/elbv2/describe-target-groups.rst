[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 describe-target-groups:


**********************
describe-target-groups
**********************



===========
Description
===========



Describes the specified target groups or all of your target groups. By default, all target groups are described. Alternatively, you can specify one of the following to filter the results: the ARN of the load balancer, the names of one or more target groups, or the ARNs of one or more target groups.

 

To describe the targets for a target group, use  describe-target-health . To describe the attributes of a target group, use  describe-target-group-attributes .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/DescribeTargetGroups>`_


``describe-target-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``TargetGroups``


========
Synopsis
========

::

    describe-target-groups
  [--load-balancer-arn <value>]
  [--target-group-arns <value>]
  [--names <value>]
  [--page-size <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-arn`` (string)


  The Amazon Resource Name (ARN) of the load balancer.

  

``--target-group-arns`` (list)


  The Amazon Resource Names (ARN) of the target groups.

  



Syntax::

  "string" "string" ...



``--names`` (list)


  The names of the target groups.

  



Syntax::

  "string" "string" ...



``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a target group**

This example describes the specified target group.

Command::

  aws elbv2 describe-target-groups --target-group-arns arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067

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
            "LoadBalancerArns": [
                "arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188"
            ],
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

**To describe all target groups for a load balancer**

This example describes all target groups for the specified load balancer.

Command::

  aws elbv2 describe-target-groups --load-balancer-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188

**To describe all target groups**

This example describes all of your target groups.

Command::

  aws elbv2 describe-target-groups 


======
Output
======

TargetGroups -> (list)

  

  Information about the target groups.

  

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

        

        

      

    

  

NextMarker -> (string)

  

  The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

  

  

