[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling put-scaling-policy:


******************
put-scaling-policy
******************



===========
Description
===========



Creates or updates a policy for an Auto Scaling group. To update an existing policy, use the existing policy name and set the parameters you want to change. Any existing parameter not changed in an update to an existing policy is not changed in this update request.

 

If you exceed your maximum limit of step adjustments, which by default is 20 per region, the call fails. For information about updating this limit, see `AWS Service Limits <http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html>`_ in the *Amazon Web Services General Reference* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/PutScalingPolicy>`_


========
Synopsis
========

::

    put-scaling-policy
  --auto-scaling-group-name <value>
  --policy-name <value>
  [--policy-type <value>]
  [--adjustment-type <value>]
  [--min-adjustment-step <value>]
  [--min-adjustment-magnitude <value>]
  [--scaling-adjustment <value>]
  [--cooldown <value>]
  [--metric-aggregation-type <value>]
  [--step-adjustments <value>]
  [--estimated-instance-warmup <value>]
  [--target-tracking-configuration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name or ARN of the group.

  

``--policy-name`` (string)


  The name of the policy.

  

``--policy-type`` (string)


  The policy type. The valid values are ``SimpleScaling`` , ``StepScaling`` , and ``TargetTrackingScaling`` . If the policy type is null, the value is treated as ``SimpleScaling`` .

  

``--adjustment-type`` (string)


  The adjustment type. The valid values are ``ChangeInCapacity`` , ``ExactCapacity`` , and ``PercentChangeInCapacity`` .

   

  This parameter is supported if the policy type is ``SimpleScaling`` or ``StepScaling`` .

   

  For more information, see `Dynamic Scaling <http://docs.aws.amazon.com/autoscaling/latest/userguide/as-scale-based-on-demand.html>`_ in the *Auto Scaling User Guide* .

  

``--min-adjustment-step`` (integer)


  Available for backward compatibility. Use ``min-adjustment-magnitude`` instead.

  

``--min-adjustment-magnitude`` (integer)


  The minimum number of instances to scale. If the value of ``AdjustmentType`` is ``PercentChangeInCapacity`` , the scaling policy changes the ``DesiredCapacity`` of the Auto Scaling group by at least this many instances. Otherwise, the error is ``ValidationError`` .

   

  This parameter is supported if the policy type is ``SimpleScaling`` or ``StepScaling`` .

  

``--scaling-adjustment`` (integer)


  The amount by which to scale, based on the specified adjustment type. A positive value adds to the current capacity while a negative number removes from the current capacity.

   

  This parameter is required if the policy type is ``SimpleScaling`` and not supported otherwise.

  

``--cooldown`` (integer)


  The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start. If this parameter is not specified, the default cooldown period for the group applies.

   

  This parameter is supported if the policy type is ``SimpleScaling`` .

   

  For more information, see `Auto Scaling Cooldowns <http://docs.aws.amazon.com/autoscaling/latest/userguide/Cooldown.html>`_ in the *Auto Scaling User Guide* .

  

``--metric-aggregation-type`` (string)


  The aggregation type for the CloudWatch metrics. The valid values are ``Minimum`` , ``Maximum`` , and ``Average`` . If the aggregation type is null, the value is treated as ``Average`` .

   

  This parameter is supported if the policy type is ``StepScaling`` .

  

``--step-adjustments`` (list)


  A set of adjustments that enable you to scale based on the size of the alarm breach.

   

  This parameter is required if the policy type is ``StepScaling`` and not supported otherwise.

  



Shorthand Syntax::

    MetricIntervalLowerBound=double,MetricIntervalUpperBound=double,ScalingAdjustment=integer ...




JSON Syntax::

  [
    {
      "MetricIntervalLowerBound": double,
      "MetricIntervalUpperBound": double,
      "ScalingAdjustment": integer
    }
    ...
  ]



``--estimated-instance-warmup`` (integer)


  The estimated time, in seconds, until a newly launched instance can contribute to the CloudWatch metrics. The default is to use the value specified for the default cooldown period for the group.

   

  This parameter is supported if the policy type is ``StepScaling`` or ``TargetTrackingScaling`` .

  

``--target-tracking-configuration`` (structure)


  The configuration of a target tracking policy.

   

  This parameter is required if the policy type is ``TargetTrackingScaling`` and not supported otherwise.

  



JSON Syntax::

  {
    "PredefinedMetricSpecification": {
      "PredefinedMetricType": "ASGAverageCPUUtilization"|"ASGAverageNetworkIn"|"ASGAverageNetworkOut"|"ALBRequestCountPerTarget",
      "ResourceLabel": "string"
    },
    "CustomizedMetricSpecification": {
      "MetricName": "string",
      "Namespace": "string",
      "Dimensions": [
        {
          "Name": "string",
          "Value": "string"
        }
        ...
      ],
      "Statistic": "Average"|"Minimum"|"Maximum"|"SampleCount"|"Sum",
      "Unit": "string"
    },
    "TargetValue": double,
    "DisableScaleIn": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add a scaling policy to an Auto Scaling group**

This example adds the specified policy to the specified Auto Scaling group::

    aws autoscaling put-scaling-policy --auto-scaling-group-name my-auto-scaling-group --policy-name ScaleIn --scaling-adjustment -1 --adjustment-type ChangeInCapacity

To change the size of the Auto Scaling group by a specific number of instances, set the ``adjustment-type`` parameter to ``PercentChangeInCapacity``. Then, assign a value to
the ``min-adjustment-step`` parameter, where the value represents the number of instances the policy adds or removes from the Auto Scaling group::

    aws autoscaling put-scaling-policy --auto-scaling-group-name my-auto-scaling-group --policy-name ScalePercentChange --scaling-adjustment 25 --adjustment-type PercentChangeInCapacity --cooldown 60 --min-adjustment-step 2

The output includes the ARN of the policy. The following is example output::

    {
        "PolicyARN": "arn:aws:autoscaling:us-west-2:123456789012:scalingPolicy:2233f3d7-6290-403b-b632-93c553560106:autoScalingGroupName/my-auto-scaling-group:policyName/ScaleIn"
    }

For more information, see `Dynamic Scaling`_ in the *Auto Scaling Developer Guide*.

.. _`Dynamic Scaling`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html


======
Output
======

PolicyARN -> (string)

  

  The Amazon Resource Name (ARN) of the policy.

  

  

Alarms -> (list)

  

  The CloudWatch alarms created for the target tracking policy. This parameter will be empty if the policy type is anything other than ``TargetTrackingScaling`` .

  

  (structure)

    

    Describes an alarm.

    

    AlarmName -> (string)

      

      The name of the alarm.

      

      

    AlarmARN -> (string)

      

      The Amazon Resource Name (ARN) of the alarm.

      

      

    

  

