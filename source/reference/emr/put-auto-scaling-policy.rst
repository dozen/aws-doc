[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr put-auto-scaling-policy:


***********************
put-auto-scaling-policy
***********************



===========
Description
===========



Creates or updates an automatic scaling policy for a core instance group or task instance group in an Amazon EMR cluster. The automatic scaling policy defines how an instance group dynamically adds and terminates EC2 instances in response to the value of a CloudWatch metric.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/PutAutoScalingPolicy>`_


========
Synopsis
========

::

    put-auto-scaling-policy
  --cluster-id <value>
  --instance-group-id <value>
  --auto-scaling-policy <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  Specifies the ID of a cluster. The instance group to which the automatic scaling policy is applied is within this cluster.

  

``--instance-group-id`` (string)


  Specifies the ID of the instance group to which the automatic scaling policy is applied.

  

``--auto-scaling-policy`` (structure)


  Specifies the definition of the automatic scaling policy.

  



JSON Syntax::

  {
    "Constraints": {
      "MinCapacity": integer,
      "MaxCapacity": integer
    },
    "Rules": [
      {
        "Name": "string",
        "Description": "string",
        "Action": {
          "Market": "ON_DEMAND"|"SPOT",
          "SimpleScalingPolicyConfiguration": {
            "AdjustmentType": "CHANGE_IN_CAPACITY"|"PERCENT_CHANGE_IN_CAPACITY"|"EXACT_CAPACITY",
            "ScalingAdjustment": integer,
            "CoolDown": integer
          }
        },
        "Trigger": {
          "CloudWatchAlarmDefinition": {
            "ComparisonOperator": "GREATER_THAN_OR_EQUAL"|"GREATER_THAN"|"LESS_THAN"|"LESS_THAN_OR_EQUAL",
            "EvaluationPeriods": integer,
            "MetricName": "string",
            "Namespace": "string",
            "Period": integer,
            "Statistic": "SAMPLE_COUNT"|"AVERAGE"|"SUM"|"MINIMUM"|"MAXIMUM",
            "Threshold": double,
            "Unit": "NONE"|"SECONDS"|"MICRO_SECONDS"|"MILLI_SECONDS"|"BYTES"|"KILO_BYTES"|"MEGA_BYTES"|"GIGA_BYTES"|"TERA_BYTES"|"BITS"|"KILO_BITS"|"MEGA_BITS"|"GIGA_BITS"|"TERA_BITS"|"PERCENT"|"COUNT"|"BYTES_PER_SECOND"|"KILO_BYTES_PER_SECOND"|"MEGA_BYTES_PER_SECOND"|"GIGA_BYTES_PER_SECOND"|"TERA_BYTES_PER_SECOND"|"BITS_PER_SECOND"|"KILO_BITS_PER_SECOND"|"MEGA_BITS_PER_SECOND"|"GIGA_BITS_PER_SECOND"|"TERA_BITS_PER_SECOND"|"COUNT_PER_SECOND",
            "Dimensions": [
              {
                "Key": "string",
                "Value": "string"
              }
              ...
            ]
          }
        }
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ClusterId -> (string)

  

  Specifies the ID of a cluster. The instance group to which the automatic scaling policy is applied is within this cluster.

  

  

InstanceGroupId -> (string)

  

  Specifies the ID of the instance group to which the scaling policy is applied.

  

  

AutoScalingPolicy -> (structure)

  

  The automatic scaling policy definition.

  

  Status -> (structure)

    

    The status of an automatic scaling policy. 

    

    State -> (string)

      

      Indicates the status of the automatic scaling policy.

      

      

    StateChangeReason -> (structure)

      

      The reason for a change in status.

      

      Code -> (string)

        

        The code indicating the reason for the change in status.``USER_REQUEST`` indicates that the scaling policy status was changed by a user. ``PROVISION_FAILURE`` indicates that the status change was because the policy failed to provision. ``CLEANUP_FAILURE`` indicates an error.

        

        

      Message -> (string)

        

        A friendly, more verbose message that accompanies an automatic scaling policy state change.

        

        

      

    

  Constraints -> (structure)

    

    The upper and lower EC2 instance limits for an automatic scaling policy. Automatic scaling activity will not cause an instance group to grow above or below these limits.

    

    MinCapacity -> (integer)

      

      The lower boundary of EC2 instances in an instance group below which scaling activities are not allowed to shrink. Scale-in activities will not terminate instances below this boundary.

      

      

    MaxCapacity -> (integer)

      

      The upper boundary of EC2 instances in an instance group beyond which scaling activities are not allowed to grow. Scale-out activities will not add instances beyond this boundary.

      

      

    

  Rules -> (list)

    

    The scale-in and scale-out rules that comprise the automatic scaling policy.

    

    (structure)

      

      A scale-in or scale-out rule that defines scaling activity, including the CloudWatch metric alarm that triggers activity, how EC2 instances are added or removed, and the periodicity of adjustments. The automatic scaling policy for an instance group can comprise one or more automatic scaling rules.

      

      Name -> (string)

        

        The name used to identify an automatic scaling rule. Rule names must be unique within a scaling policy.

        

        

      Description -> (string)

        

        A friendly, more verbose description of the automatic scaling rule.

        

        

      Action -> (structure)

        

        The conditions that trigger an automatic scaling activity.

        

        Market -> (string)

          

          Not available for instance groups. Instance groups use the market type specified for the group.

          

          

        SimpleScalingPolicyConfiguration -> (structure)

          

          The type of adjustment the automatic scaling activity makes when triggered, and the periodicity of the adjustment.

          

          AdjustmentType -> (string)

            

            The way in which EC2 instances are added (if ``ScalingAdjustment`` is a positive number) or terminated (if ``ScalingAdjustment`` is a negative number) each time the scaling activity is triggered. ``CHANGE_IN_CAPACITY`` is the default. ``CHANGE_IN_CAPACITY`` indicates that the EC2 instance count increments or decrements by ``ScalingAdjustment`` , which should be expressed as an integer. ``PERCENT_CHANGE_IN_CAPACITY`` indicates the instance count increments or decrements by the percentage specified by ``ScalingAdjustment`` , which should be expressed as a decimal. For example, 0.20 indicates an increase in 20% increments of cluster capacity. ``EXACT_CAPACITY`` indicates the scaling activity results in an instance group with the number of EC2 instances specified by ``ScalingAdjustment`` , which should be expressed as a positive integer.

            

            

          ScalingAdjustment -> (integer)

            

            The amount by which to scale in or scale out, based on the specified ``AdjustmentType`` . A positive value adds to the instance group's EC2 instance count while a negative number removes instances. If ``AdjustmentType`` is set to ``EXACT_CAPACITY`` , the number should only be a positive integer. If ``AdjustmentType`` is set to ``PERCENT_CHANGE_IN_CAPACITY`` , the value should express the percentage as a decimal. For example, -0.20 indicates a decrease in 20% increments of cluster capacity.

            

            

          CoolDown -> (integer)

            

            The amount of time, in seconds, after a scaling activity completes before any further trigger-related scaling activities can start. The default value is 0.

            

            

          

        

      Trigger -> (structure)

        

        The CloudWatch alarm definition that determines when automatic scaling activity is triggered.

        

        CloudWatchAlarmDefinition -> (structure)

          

          The definition of a CloudWatch metric alarm. When the defined alarm conditions are met along with other trigger parameters, scaling activity begins.

          

          ComparisonOperator -> (string)

            

            Determines how the metric specified by ``MetricName`` is compared to the value specified by ``Threshold`` .

            

            

          EvaluationPeriods -> (integer)

            

            The number of periods, expressed in seconds using ``Period`` , during which the alarm condition must exist before the alarm triggers automatic scaling activity. The default value is ``1`` .

            

            

          MetricName -> (string)

            

            The name of the CloudWatch metric that is watched to determine an alarm condition.

            

            

          Namespace -> (string)

            

            The namespace for the CloudWatch metric. The default is ``AWS/ElasticMapReduce`` .

            

            

          Period -> (integer)

            

            The period, in seconds, over which the statistic is applied. EMR CloudWatch metrics are emitted every five minutes (300 seconds), so if an EMR CloudWatch metric is specified, specify ``300`` .

            

            

          Statistic -> (string)

            

            The statistic to apply to the metric associated with the alarm. The default is ``AVERAGE`` .

            

            

          Threshold -> (double)

            

            The value against which the specified statistic is compared.

            

            

          Unit -> (string)

            

            The unit of measure associated with the CloudWatch metric being watched. The value specified for ``Unit`` must correspond to the units specified in the CloudWatch metric.

            

            

          Dimensions -> (list)

            

            A CloudWatch metric dimension.

            

            (structure)

              

              A CloudWatch dimension, which is specified using a ``Key`` (known as a ``Name`` in CloudWatch), ``Value`` pair. By default, Amazon EMR uses one dimension whose ``Key`` is ``JobFlowID`` and ``Value`` is a variable representing the cluster ID, which is ``${emr.clusterId}`` . This enables the rule to bootstrap when the cluster ID becomes available.

              

              Key -> (string)

                

                The dimension name.

                

                

              Value -> (string)

                

                The dimension value.

                

                

              

            

          

        

      

    

  

