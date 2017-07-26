[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr add-instance-groups:


*******************
add-instance-groups
*******************



===========
Description
===========

Adds an instance group to a running cluster.



========
Synopsis
========

::

    add-instance-groups
  --cluster-id <value>
  --instance-groups <value> [<value>...]




=======
Options
=======

``--cluster-id`` (string)


  A unique string that identifies the cluster. This identifier is returned by ``create-cluster`` and can also be obtained from ``list-clusters`` .

  

``--instance-groups`` (list)


  A specification of the number and type of Amazon EC2 instances to create instance groups in a cluster.

  

  Each instance group takes the following parameters: ``[Name], InstanceGroupType, InstanceType, InstanceCount, [BidPrice], [EbsConfiguration], [AutoScalingPolicy]`` . [EbsConfiguration] and [AutoScalingPolicy] are optional. EbsConfiguration takes the following parameters: ``EbsOptimized`` and ``EbsBlockDeviceConfigs`` . EbsBlockDeviceConfigs is an array of EBS volume specifications, which takes the following parameters : ``([VolumeType], [SizeInGB], Iops)`` and VolumesPerInstance which is the count of EBS volumes per instance with this specification.

  

  AutoScalingPolicy takes the following parameters: ``Constraints`` and ``Rules`` . Constraints takes the following parameters: ``MinCapacity, MaxCapacity`` . Rules is a list of AutoScaling rules associated to the policy. Each rule has the following parameters: ``Name, [Description], Action, Trigger`` . Action takes the following parameters: ``Market, SimpleScalingPolicyConfiguration (AdjustmentType, ScalingAdjustment)`` . Trigger takes ``CloudWatchAlarmDefinition(AlarmNamePrefix, ComparisonOperator, EvaluationPeriods, MetricName, Namespace, Period, Statistic, Threshold, Unit, [Dimensions])`` .

  



JSON Syntax::

  [
    {
      "InstanceCount": integer,
      "Name": "string",
      "InstanceGroupType": "MASTER"|"CORE"|"TASK",
      "AutoScalingPolicy": {
        "Rules": [
          {
            "Action": {
              "SimpleScalingPolicyConfiguration": {
                "ScalingAdjustment": integer,
                "CoolDown": integer,
                "AdjustmentType": "CHANGE_IN_CAPACITY"|"PERCENT_CHANGE_IN_CAPACITY"|"EXACT_CAPACITY"
              },
              "Market": "ON_DEMAND"|"SPOT"
            },
            "Trigger": {
              "CloudWatchAlarmDefinition": {
                "EvaluationPeriods": integer,
                "Dimensions": [
                  {
                    "Key": "string",
                    "Value": "string"
                  }
                  ...
                ],
                "Namespace": "string",
                "Period": integer,
                "ComparisonOperator": "string",
                "Statistic": "string",
                "Threshold": double,
                "Unit": "string",
                "MetricName": "string"
              }
            },
            "Name": "string",
            "Description": "string"
          }
          ...
        ],
        "Constraints": {
          "MinCapacity": integer,
          "MaxCapacity": integer
        }
      },
      "EbsConfiguration": {
        "EbsOptimized": true|false,
        "EbsBlockDeviceConfigs": [
          {
            "VolumeSpecification": {
              "Iops": integer,
              "VolumeType": "string",
              "SizeInGB": integer
            },
            "VolumesPerInstance": integer
          }
          ...
        ]
      },
      "BidPrice": "string",
      "InstanceType": "string"
    }
    ...
  ]



