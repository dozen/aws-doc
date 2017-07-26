[ :ref:`aws <cli:aws>` . :ref:`application-autoscaling <cli:aws application-autoscaling>` ]

.. _cli:aws application-autoscaling put-scaling-policy:


******************
put-scaling-policy
******************



===========
Description
===========



Creates or updates a policy for an Application Auto Scaling scalable target.

 

Each scalable target is identified by a service namespace, resource ID, and scalable dimension. A scaling policy applies to the scalable target identified by those three attributes. You cannot create a scaling policy without first registering a scalable target using  register-scalable-target .

 

To update a policy, specify its policy name and the parameters that you want to change. Any parameters that you don't specify are not changed by this update request.

 

You can view the scaling policies for a service namespace using  describe-scaling-policies . If you are no longer using a scaling policy, you can delete it using  delete-scaling-policy .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/application-autoscaling-2016-02-06/PutScalingPolicy>`_


========
Synopsis
========

::

    put-scaling-policy
  --policy-name <value>
  --service-namespace <value>
  --resource-id <value>
  --scalable-dimension <value>
  [--policy-type <value>]
  [--step-scaling-policy-configuration <value>]
  [--target-tracking-scaling-policy-configuration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-name`` (string)


  The name of the scaling policy.

  

``--service-namespace`` (string)


  The namespace of the AWS service. For more information, see `AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#genref-aws-service-namespaces>`_ in the *Amazon Web Services General Reference* .

  

  Possible values:

  
  *   ``ecs``

  
  *   ``elasticmapreduce``

  
  *   ``ec2``

  
  *   ``appstream``

  
  *   ``dynamodb``

  

  

``--resource-id`` (string)


  The identifier of the resource associated with the scaling policy. This string consists of the resource type and unique identifier.

   

   
  * ECS service - The resource type is ``service`` and the unique identifier is the cluster name and service name. Example: ``service/default/sample-webapp`` . 
   
  * Spot fleet request - The resource type is ``spot-fleet-request`` and the unique identifier is the Spot fleet request ID. Example: ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` . 
   
  * EMR cluster - The resource type is ``instancegroup`` and the unique identifier is the cluster ID and instance group ID. Example: ``instancegroup/j-2EEZNYKUA1NTV/ig-1791Y4E1L8YI0`` . 
   
  * AppStream 2.0 fleet - The resource type is ``fleet`` and the unique identifier is the fleet name. Example: ``fleet/sample-fleet`` . 
   
  * DynamoDB table - The resource type is ``table`` and the unique identifier is the resource ID. Example: ``table/my-table`` . 
   
  * DynamoDB global secondary index - The resource type is ``index`` and the unique identifier is the resource ID. Example: ``table/my-table/index/my-table-index`` . 
   

  

``--scalable-dimension`` (string)


  The scalable dimension. This string consists of the service namespace, resource type, and scaling property.

   

   
  * ``ecs:service:DesiredCount`` - The desired task count of an ECS service. 
   
  * ``ec2:spot-fleet-request:TargetCapacity`` - The target capacity of a Spot fleet request. 
   
  * ``elasticmapreduce:instancegroup:InstanceCount`` - The instance count of an EMR Instance Group. 
   
  * ``appstream:fleet:DesiredCapacity`` - The desired capacity of an AppStream 2.0 fleet. 
   
  * ``dynamodb:table:ReadCapacityUnits`` - The provisioned read capacity for a DynamoDB table. 
   
  * ``dynamodb:table:WriteCapacityUnits`` - The provisioned write capacity for a DynamoDB table. 
   
  * ``dynamodb:index:ReadCapacityUnits`` - The provisioned read capacity for a DynamoDB global secondary index. 
   
  * ``dynamodb:index:WriteCapacityUnits`` - The provisioned write capacity for a DynamoDB global secondary index. 
   

  

  Possible values:

  
  *   ``ecs:service:DesiredCount``

  
  *   ``ec2:spot-fleet-request:TargetCapacity``

  
  *   ``elasticmapreduce:instancegroup:InstanceCount``

  
  *   ``appstream:fleet:DesiredCapacity``

  
  *   ``dynamodb:table:ReadCapacityUnits``

  
  *   ``dynamodb:table:WriteCapacityUnits``

  
  *   ``dynamodb:index:ReadCapacityUnits``

  
  *   ``dynamodb:index:WriteCapacityUnits``

  

  

``--policy-type`` (string)


  The policy type. If you are creating a new policy, this parameter is required. If you are updating a policy, this parameter is not required.

   

  For DynamoDB, only ``TargetTrackingScaling`` is supported. For any other service, only ``StepScaling`` is supported.

  

  Possible values:

  
  *   ``StepScaling``

  
  *   ``TargetTrackingScaling``

  

  

``--step-scaling-policy-configuration`` (structure)


  A step scaling policy.

   

  This parameter is required if you are creating a policy and the policy type is ``StepScaling`` .

  



Shorthand Syntax::

    AdjustmentType=string,StepAdjustments=[{MetricIntervalLowerBound=double,MetricIntervalUpperBound=double,ScalingAdjustment=integer},{MetricIntervalLowerBound=double,MetricIntervalUpperBound=double,ScalingAdjustment=integer}],MinAdjustmentMagnitude=integer,Cooldown=integer,MetricAggregationType=string




JSON Syntax::

  {
    "AdjustmentType": "ChangeInCapacity"|"PercentChangeInCapacity"|"ExactCapacity",
    "StepAdjustments": [
      {
        "MetricIntervalLowerBound": double,
        "MetricIntervalUpperBound": double,
        "ScalingAdjustment": integer
      }
      ...
    ],
    "MinAdjustmentMagnitude": integer,
    "Cooldown": integer,
    "MetricAggregationType": "Average"|"Minimum"|"Maximum"
  }



``--target-tracking-scaling-policy-configuration`` (structure)


  A target tracking policy.

   

  This parameter is required if you are creating a new policy and the policy type is ``TargetTrackingScaling`` .

  



JSON Syntax::

  {
    "TargetValue": double,
    "PredefinedMetricSpecification": {
      "PredefinedMetricType": "DynamoDBReadCapacityUtilization"|"DynamoDBWriteCapacityUtilization",
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
    "ScaleOutCooldown": integer,
    "ScaleInCooldown": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To apply a scaling policy to an Amazon ECS service**

This example command applies a scaling policy to an Amazon ECS service called `web-app` in the `default` cluster. The policy increases the desired count of the service by 200%, with a cool down period of 60 seconds.

Command::

  aws application-autoscaling put-scaling-policy --cli-input-json file://scale-out.json

Contents of `scale-out.json` file::

  {
      "PolicyName": "web-app-cpu-gt-75",
      "ServiceNamespace": "ecs",
      "ResourceId": "service/default/web-app",
      "ScalableDimension": "ecs:service:DesiredCount",
      "PolicyType": "StepScaling",
      "StepScalingPolicyConfiguration": {
          "AdjustmentType": "PercentChangeInCapacity",
          "StepAdjustments": [
              {
  				"MetricIntervalLowerBound": 0,
  				"ScalingAdjustment": 200
              }
          ],
          "Cooldown": 60
      }
  }

Output::

  {
      "PolicyARN": "arn:aws:autoscaling:us-west-2:012345678910:scalingPolicy:6d8972f3-efc8-437c-92d1-6270f29a66e7:resource/ecs/service/default/web-app:policyName/web-app-cpu-gt-75"
  }


======
Output
======

PolicyARN -> (string)

  

  The Amazon Resource Name (ARN) of the resulting scaling policy.

  

  

Alarms -> (list)

  

  The CloudWatch alarms created for the target tracking policy.

  

  (structure)

    

    Represents a CloudWatch alarm associated with a scaling policy.

    

    AlarmName -> (string)

      

      The name of the alarm.

      

      

    AlarmARN -> (string)

      

      The Amazon Resource Name (ARN) of the alarm.

      

      

    

  

