[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-policies:


*****************
describe-policies
*****************



===========
Description
===========



Describes the policies for the specified Auto Scaling group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribePolicies>`_


``describe-policies`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ScalingPolicies``


========
Synopsis
========

::

    describe-policies
  [--auto-scaling-group-name <value>]
  [--policy-names <value>]
  [--policy-types <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the group.

  

``--policy-names`` (list)


  One or more policy names or policy ARNs to be described. If you omit this parameter, all policy names are described. If an group name is provided, the results are limited to that group. This list is limited to 50 items. If you specify an unknown policy name, it is ignored with no error.

  



Syntax::

  "string" "string" ...



``--policy-types`` (list)


  One or more policy types. Valid values are ``SimpleScaling`` and ``StepScaling`` .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe Auto Scaling policies**

This example describes the policies for the specified Auto Scaling group::

    aws autoscaling describe-policies --auto-scaling-group-name my-auto-scaling-group

The following is example output::

    {
        "ScalingPolicies": [
            {
                "PolicyName": "ScaleIn",
                "AutoScalingGroupName": "my-auto-scaling-group",
                "PolicyARN": "arn:aws:autoscaling:us-west-2:123456789012:scalingPolicy:2233f3d7-6290-403b-b632-93c553560106:autoScalingGroupName/my-auto-scaling-group:policyName/ScaleIn",
                "AdjustmentType": "ChangeInCapacity",
                "Alarms": [],
                "ScalingAdjustment": -1
            },
            {
                "PolicyName": "ScalePercentChange",
                "MinAdjustmentStep": 2,
                "AutoScalingGroupName": "my-auto-scaling-group",
                "PolicyARN": "arn:aws:autoscaling:us-west-2:123456789012:scalingPolicy:2b435159-cf77-4e89-8c0e-d63b497baad7:autoScalingGroupName/my-auto-scaling-group:policyName/ScalePercentChange",
                "Cooldown": 60,
                "AdjustmentType": "PercentChangeInCapacity",
                "Alarms": [],
                "ScalingAdjustment": 25
            }
        ]
    }

To return specific scaling policies, use the ``policy-names`` parameter::

    aws autoscaling describe-policies --auto-scaling-group-name my-auto-scaling-group --policy-names ScaleIn

To return a specific number of policies, use the ``max-items`` parameter::

    aws autoscaling describe-policies --auto-scaling-group-name my-auto-scaling-group --max-items 1

The following is example output::

    {
        "ScalingPolicies": [
            {
                "PolicyName": "ScaleIn",
                "AutoScalingGroupName": "my-auto-scaling-group",
                "PolicyARN": "arn:aws:autoscaling:us-west-2:123456789012:scalingPolicy:2233f3d7-6290-403b-b632-93c553560106:autoScalingGroupName/my-auto-scaling-group:policyName/ScaleIn",
                "AdjustmentType": "ChangeInCapacity",
                "Alarms": [],
                "ScalingAdjustment": -1
            }
        ],
        "NextToken": "Z3M3LMPEXAMPLE"
    }

If the output includes a ``NextToken`` field, use the value of this field with the ``starting-token`` parameter in a subsequent call to get the additional policies::

    aws autoscaling describe-policies --auto-scaling-group-name my-auto-scaling-group --starting-token Z3M3LMPEXAMPLE

For more information, see `Dynamic Scaling`_ in the *Auto Scaling Developer Guide*.

.. _`Dynamic Scaling`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html


======
Output
======

ScalingPolicies -> (list)

  

  The scaling policies.

  

  (structure)

    

    Describes a scaling policy.

    

    AutoScalingGroupName -> (string)

      

      The name of the Auto Scaling group associated with this scaling policy.

      

      

    PolicyName -> (string)

      

      The name of the scaling policy.

      

      

    PolicyARN -> (string)

      

      The Amazon Resource Name (ARN) of the policy.

      

      

    PolicyType -> (string)

      

      The policy type. Valid values are ``SimpleScaling`` and ``StepScaling`` .

      

      

    AdjustmentType -> (string)

      

      The adjustment type, which specifies how ``ScalingAdjustment`` is interpreted. Valid values are ``ChangeInCapacity`` , ``ExactCapacity`` , and ``PercentChangeInCapacity`` .

      

      

    MinAdjustmentStep -> (integer)

      

      Available for backward compatibility. Use ``MinAdjustmentMagnitude`` instead.

      

      

    MinAdjustmentMagnitude -> (integer)

      

      The minimum number of instances to scale. If the value of ``AdjustmentType`` is ``PercentChangeInCapacity`` , the scaling policy changes the ``DesiredCapacity`` of the Auto Scaling group by at least this many instances. Otherwise, the error is ``ValidationError`` .

      

      

    ScalingAdjustment -> (integer)

      

      The amount by which to scale, based on the specified adjustment type. A positive value adds to the current capacity while a negative number removes from the current capacity.

      

      

    Cooldown -> (integer)

      

      The amount of time, in seconds, after a scaling activity completes before any further trigger-related scaling activities can start.

      

      

    StepAdjustments -> (list)

      

      A set of adjustments that enable you to scale based on the size of the alarm breach.

      

      (structure)

        

        Describes an adjustment based on the difference between the value of the aggregated CloudWatch metric and the breach threshold that you've defined for the alarm.

         

        For the following examples, suppose that you have an alarm with a breach threshold of 50:

         

         
        * If you want the adjustment to be triggered when the metric is greater than or equal to 50 and less than 60, specify a lower bound of 0 and an upper bound of 10. 
         
        * If you want the adjustment to be triggered when the metric is greater than 40 and less than or equal to 50, specify a lower bound of -10 and an upper bound of 0. 
         

         

        There are a few rules for the step adjustments for your step policy:

         

         
        * The ranges of your step adjustments can't overlap or have a gap. 
         
        * At most one step adjustment can have a null lower bound. If one step adjustment has a negative lower bound, then there must be a step adjustment with a null lower bound. 
         
        * At most one step adjustment can have a null upper bound. If one step adjustment has a positive upper bound, then there must be a step adjustment with a null upper bound. 
         
        * The upper and lower bound can't be null in the same step adjustment. 
         

        

        MetricIntervalLowerBound -> (double)

          

          The lower bound for the difference between the alarm threshold and the CloudWatch metric. If the metric value is above the breach threshold, the lower bound is inclusive (the metric must be greater than or equal to the threshold plus the lower bound). Otherwise, it is exclusive (the metric must be greater than the threshold plus the lower bound). A null value indicates negative infinity.

          

          

        MetricIntervalUpperBound -> (double)

          

          The upper bound for the difference between the alarm threshold and the CloudWatch metric. If the metric value is above the breach threshold, the upper bound is exclusive (the metric must be less than the threshold plus the upper bound). Otherwise, it is inclusive (the metric must be less than or equal to the threshold plus the upper bound). A null value indicates positive infinity.

           

          The upper bound must be greater than the lower bound.

          

          

        ScalingAdjustment -> (integer)

          

          The amount by which to scale, based on the specified adjustment type. A positive value adds to the current capacity while a negative number removes from the current capacity.

          

          

        

      

    MetricAggregationType -> (string)

      

      The aggregation type for the CloudWatch metrics. Valid values are ``Minimum`` , ``Maximum`` , and ``Average`` .

      

      

    EstimatedInstanceWarmup -> (integer)

      

      The estimated time, in seconds, until a newly launched instance can contribute to the CloudWatch metrics.

      

      

    Alarms -> (list)

      

      The CloudWatch alarms related to the policy.

      

      (structure)

        

        Describes an alarm.

        

        AlarmName -> (string)

          

          The name of the alarm.

          

          

        AlarmARN -> (string)

          

          The Amazon Resource Name (ARN) of the alarm.

          

          

        

      

    TargetTrackingConfiguration -> (structure)

      

      A target tracking policy.

      

      PredefinedMetricSpecification -> (structure)

        

        A predefined metric. You can specify either a predefined metric or a customized metric.

        

        PredefinedMetricType -> (string)

          

          The metric type.

          

          

        ResourceLabel -> (string)

          

          Identifies the resource associated with the metric type. For predefined metric types ``ASGAverageCPUUtilization`` , ``ASGAverageNetworkIn`` and ``ASGAverageNetworkOut`` , the parameter must not be specified as the resource associated with the metric type is the Auto Scaling group. For predefined metric type ``ALBRequestCountPerTarget`` , the parameter must be specified in the format ``app/*load-balancer-name* /*load-balancer-id* /targetgroup/*target-group-name* /*target-group-id* `` , where ``app/*load-balancer-name* /*load-balancer-id* `` is the final portion of the load balancer ARN, and ``targetgroup/*target-group-name* /*target-group-id* `` is the final portion of the target group ARN. The target group must be attached to the Auto Scaling group.

          

          

        

      CustomizedMetricSpecification -> (structure)

        

        A customized metric.

        

        MetricName -> (string)

          

          The name of the metric.

          

          

        Namespace -> (string)

          

          The namespace of the metric.

          

          

        Dimensions -> (list)

          

          The dimensions of the metric.

          

          (structure)

            

            Describes the dimension of a metric.

            

            Name -> (string)

              

              The name of the dimension.

              

              

            Value -> (string)

              

              The value of the dimension.

              

              

            

          

        Statistic -> (string)

          

          The statistic of the metric.

          

          

        Unit -> (string)

          

          The unit of the metric.

          

          

        

      TargetValue -> (double)

        

        The target value for the metric.

        

        

      DisableScaleIn -> (boolean)

        

        If the parameter is true, then scale-in will be disabled for the target tracking policy, i.e. the target tracking policy will not scale in the Auto Scaling group. The default value is false.

        

        

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

