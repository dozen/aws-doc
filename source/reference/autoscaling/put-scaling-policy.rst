[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling put-scaling-policy:


******************
put-scaling-policy
******************



===========
Description
===========



Creates or updates a policy for an Auto Scaling group. To update an existing policy, use the existing policy name and set the parameters you want to change. Any existing parameter not changed in an update to an existing policy is not changed in this update request.

 

If you exceed your maximum limit of step adjustments, which by default is 20 per region, the call fails. For information about updating this limit, see `AWS Service Limits`_ in the *Amazon Web Services General Reference* .



========
Synopsis
========

::

    put-scaling-policy
  --auto-scaling-group-name <value>
  --policy-name <value>
  [--policy-type <value>]
  --adjustment-type <value>
  [--min-adjustment-step <value>]
  [--min-adjustment-magnitude <value>]
  [--scaling-adjustment <value>]
  [--cooldown <value>]
  [--metric-aggregation-type <value>]
  [--step-adjustments <value>]
  [--estimated-instance-warmup <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name or ARN of the group.

  

``--policy-name`` (string)


  The name of the policy.

  

``--policy-type`` (string)


  The policy type. Valid values are ``SimpleScaling`` and ``StepScaling`` . If the policy type is null, the value is treated as ``SimpleScaling`` .

  

``--adjustment-type`` (string)


  The adjustment type. Valid values are ``ChangeInCapacity`` , ``ExactCapacity`` , and ``PercentChangeInCapacity`` .

   

  For more information, see `Dynamic Scaling`_ in the *Auto Scaling Developer Guide* .

  

``--min-adjustment-step`` (integer)


  Available for backward compatibility. Use ``min-adjustment-magnitude`` instead.

  

``--min-adjustment-magnitude`` (integer)


  The minimum number of instances to scale. If the value of ``AdjustmentType`` is ``PercentChangeInCapacity`` , the scaling policy changes the ``DesiredCapacity`` of the Auto Scaling group by at least this many instances. Otherwise, the error is ``ValidationError`` .

  

``--scaling-adjustment`` (integer)


  The amount by which to scale, based on the specified adjustment type. A positive value adds to the current capacity while a negative number removes from the current capacity.

   

  This parameter is required if the policy type is ``SimpleScaling`` and not supported otherwise.

  

``--cooldown`` (integer)


  The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start. If this parameter is not specified, the default cooldown period for the group applies.

   

  This parameter is not supported unless the policy type is ``SimpleScaling`` .

   

  For more information, see `Auto Scaling Cooldowns`_ in the *Auto Scaling Developer Guide* .

  

``--metric-aggregation-type`` (string)


  The aggregation type for the CloudWatch metrics. Valid values are ``Minimum`` , ``Maximum`` , and ``Average`` . If the aggregation type is null, the value is treated as ``Average`` .

   

  This parameter is not supported if the policy type is ``SimpleScaling`` .

  

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

   

  This parameter is not supported if the policy type is ``SimpleScaling`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  



.. _Auto Scaling Cooldowns: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/Cooldown.html
.. _Dynamic Scaling: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html
.. _AWS Service Limits: http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html
