[ :ref:`aws <cli:aws>` . :ref:`application-autoscaling <cli:aws application-autoscaling>` ]

.. _cli:aws application-autoscaling describe-scaling-policies:


*************************
describe-scaling-policies
*************************



===========
Description
===========



Provides descriptive information about the scaling policies in the specified namespace.

 

You can filter the results using the ``ResourceId`` , ``scalable-dimension`` , and ``PolicyNames`` parameters.

 

To create a scaling policy or update an existing one, see  put-scaling-policy . If you are no longer using a scaling policy, you can delete it using  delete-scaling-policy .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/application-autoscaling-2016-02-06/DescribeScalingPolicies>`_


``describe-scaling-policies`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ScalingPolicies``


========
Synopsis
========

::

    describe-scaling-policies
  [--policy-names <value>]
  --service-namespace <value>
  [--resource-id <value>]
  [--scalable-dimension <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-names`` (list)


  The names of the scaling policies to describe.

  



Syntax::

  "string" "string" ...



``--service-namespace`` (string)


  The namespace of the AWS service. For more information, see `AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#genref-aws-service-namespaces>`_ in the *Amazon Web Services General Reference* .

  

  Possible values:

  
  *   ``ecs``

  
  *   ``elasticmapreduce``

  
  *   ``ec2``

  
  *   ``appstream``

  
  *   ``dynamodb``

  

  

``--resource-id`` (string)


  The identifier of the resource associated with the scaling policy. This string consists of the resource type and unique identifier. If you specify a scalable dimension, you must also specify a resource ID.

   

   
  * ECS service - The resource type is ``service`` and the unique identifier is the cluster name and service name. Example: ``service/default/sample-webapp`` . 
   
  * Spot fleet request - The resource type is ``spot-fleet-request`` and the unique identifier is the Spot fleet request ID. Example: ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` . 
   
  * EMR cluster - The resource type is ``instancegroup`` and the unique identifier is the cluster ID and instance group ID. Example: ``instancegroup/j-2EEZNYKUA1NTV/ig-1791Y4E1L8YI0`` . 
   
  * AppStream 2.0 fleet - The resource type is ``fleet`` and the unique identifier is the fleet name. Example: ``fleet/sample-fleet`` . 
   
  * DynamoDB table - The resource type is ``table`` and the unique identifier is the resource ID. Example: ``table/my-table`` . 
   
  * DynamoDB global secondary index - The resource type is ``index`` and the unique identifier is the resource ID. Example: ``table/my-table/index/my-table-index`` . 
   

  

``--scalable-dimension`` (string)


  The scalable dimension. This string consists of the service namespace, resource type, and scaling property. If you specify a scalable dimension, you must also specify a resource ID.

   

   
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

**To describe scaling policies**

This example command describes the scaling policies for the `ecs` service namespace.

Command::

  aws application-autoscaling describe-scaling-policies --service-namespace ecs

Output::

  {
      "ScalingPolicies": [
          {
              "PolicyName": "web-app-cpu-gt-75",
              "ScalableDimension": "ecs:service:DesiredCount",
              "ResourceId": "service/default/web-app",
              "CreationTime": 1462561899.23,
              "StepScalingPolicyConfiguration": {
                  "Cooldown": 60,
                  "StepAdjustments": [
                      {
                          "ScalingAdjustment": 200,
                          "MetricIntervalLowerBound": 0.0
                      }
                  ],
                  "AdjustmentType": "PercentChangeInCapacity"
              },
              "PolicyARN": "arn:aws:autoscaling:us-west-2:012345678910:scalingPolicy:6d8972f3-efc8-437c-92d1-6270f29a66e7:resource/ecs/service/default/web-app:policyName/web-app-cpu-gt-75",
              "PolicyType": "StepScaling",
              "Alarms": [
                  {
                      "AlarmName": "web-app-cpu-gt-75",
                      "AlarmARN": "arn:aws:cloudwatch:us-west-2:012345678910:alarm:web-app-cpu-gt-75"
                  }
              ],
              "ServiceNamespace": "ecs"
          },
          {
              "PolicyName": "web-app-cpu-lt-25",
              "ScalableDimension": "ecs:service:DesiredCount",
              "ResourceId": "service/default/web-app",
              "CreationTime": 1462562575.099,
              "StepScalingPolicyConfiguration": {
                  "Cooldown": 1,
                  "StepAdjustments": [
                      {
                          "ScalingAdjustment": -50,
                          "MetricIntervalUpperBound": 0.0
                      }
                  ],
                  "AdjustmentType": "PercentChangeInCapacity"
              },
              "PolicyARN": "arn:aws:autoscaling:us-west-2:012345678910:scalingPolicy:6d8972f3-efc8-437c-92d1-6270f29a66e7:resource/ecs/service/default/web-app:policyName/web-app-cpu-lt-25",
              "PolicyType": "StepScaling",
              "Alarms": [
                  {
                      "AlarmName": "web-app-cpu-lt-25",
                      "AlarmARN": "arn:aws:cloudwatch:us-west-2:012345678910:alarm:web-app-cpu-lt-25"
                  }
              ],
              "ServiceNamespace": "ecs"
          }
      ]
  }


======
Output
======

ScalingPolicies -> (list)

  

  A list of scaling policy objects.

  

  (structure)

    

    Represents a scaling policy.

    

    PolicyARN -> (string)

      

      The Amazon Resource Name (ARN) of the scaling policy.

      

      

    PolicyName -> (string)

      

      The name of the scaling policy.

      

      

    ServiceNamespace -> (string)

      

      The namespace of the AWS service. For more information, see `AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#genref-aws-service-namespaces>`_ in the *Amazon Web Services General Reference* .

      

      

    ResourceId -> (string)

      

      The identifier of the resource associated with the scaling policy. This string consists of the resource type and unique identifier.

       

       
      * ECS service - The resource type is ``service`` and the unique identifier is the cluster name and service name. Example: ``service/default/sample-webapp`` . 
       
      * Spot fleet request - The resource type is ``spot-fleet-request`` and the unique identifier is the Spot fleet request ID. Example: ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` . 
       
      * EMR cluster - The resource type is ``instancegroup`` and the unique identifier is the cluster ID and instance group ID. Example: ``instancegroup/j-2EEZNYKUA1NTV/ig-1791Y4E1L8YI0`` . 
       
      * AppStream 2.0 fleet - The resource type is ``fleet`` and the unique identifier is the fleet name. Example: ``fleet/sample-fleet`` . 
       
      * DynamoDB table - The resource type is ``table`` and the unique identifier is the resource ID. Example: ``table/my-table`` . 
       
      * DynamoDB global secondary index - The resource type is ``index`` and the unique identifier is the resource ID. Example: ``table/my-table/index/my-table-index`` . 
       

      

      

    ScalableDimension -> (string)

      

      The scalable dimension. This string consists of the service namespace, resource type, and scaling property.

       

       
      * ``ecs:service:DesiredCount`` - The desired task count of an ECS service. 
       
      * ``ec2:spot-fleet-request:TargetCapacity`` - The target capacity of a Spot fleet request. 
       
      * ``elasticmapreduce:instancegroup:InstanceCount`` - The instance count of an EMR Instance Group. 
       
      * ``appstream:fleet:DesiredCapacity`` - The desired capacity of an AppStream 2.0 fleet. 
       
      * ``dynamodb:table:ReadCapacityUnits`` - The provisioned read capacity for a DynamoDB table. 
       
      * ``dynamodb:table:WriteCapacityUnits`` - The provisioned write capacity for a DynamoDB table. 
       
      * ``dynamodb:index:ReadCapacityUnits`` - The provisioned read capacity for a DynamoDB global secondary index. 
       
      * ``dynamodb:index:WriteCapacityUnits`` - The provisioned write capacity for a DynamoDB global secondary index. 
       

      

      

    PolicyType -> (string)

      

      The scaling policy type.

      

      

    StepScalingPolicyConfiguration -> (structure)

      

      A step scaling policy.

      

      AdjustmentType -> (string)

        

        The adjustment type, which specifies how the ``ScalingAdjustment`` parameter in a  StepAdjustment is interpreted.

        

        

      StepAdjustments -> (list)

        

        A set of adjustments that enable you to scale based on the size of the alarm breach.

        

        (structure)

          

          Represents a step adjustment for a  StepScalingPolicyConfiguration . Describes an adjustment based on the difference between the value of the aggregated CloudWatch metric and the breach threshold that you've defined for the alarm. 

           

          For the following examples, suppose that you have an alarm with a breach threshold of 50:

           

           
          * To trigger the adjustment when the metric is greater than or equal to 50 and less than 60, specify a lower bound of 0 and an upper bound of 10. 
           
          * To trigger the adjustment when the metric is greater than 40 and less than or equal to 50, specify a lower bound of -10 and an upper bound of 0. 
           

           

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

            

            The amount by which to scale, based on the specified adjustment type. A positive value adds to the current scalable dimension while a negative number removes from the current scalable dimension.

            

            

          

        

      MinAdjustmentMagnitude -> (integer)

        

        The minimum number to adjust your scalable dimension as a result of a scaling activity. If the adjustment type is ``PercentChangeInCapacity`` , the scaling policy changes the scalable dimension of the scalable target by this amount.

        

        

      Cooldown -> (integer)

        

        The amount of time, in seconds, after a scaling activity completes where previous trigger-related scaling activities can influence future scaling events.

         

        For scale out policies, while the cooldown period is in effect, the capacity that has been added by the previous scale out event that initiated the cooldown is calculated as part of the desired capacity for the next scale out. The intention is to continuously (but not excessively) scale out. For example, an alarm triggers a step scaling policy to scale out an Amazon ECS service by 2 tasks, the scaling activity completes successfully, and a cooldown period of 5 minutes starts. During the Cooldown period, if the alarm triggers the same policy again but at a more aggressive step adjustment to scale out the service by 3 tasks, the 2 tasks that were added in the previous scale out event are considered part of that capacity and only 1 additional task is added to the desired count.

         

        For scale in policies, the cooldown period is used to block subsequent scale in requests until it has expired. The intention is to scale in conservatively to protect your application's availability. However, if another alarm triggers a scale out policy during the cooldown period after a scale-in, Application Auto Scaling scales out your scalable target immediately.

        

        

      MetricAggregationType -> (string)

        

        The aggregation type for the CloudWatch metrics. Valid values are ``Minimum`` , ``Maximum`` , and ``Average`` .

        

        

      

    TargetTrackingScalingPolicyConfiguration -> (structure)

      

      A target tracking policy.

      

      TargetValue -> (double)

        

        The target value for the metric. The range is 8.515920e-109 to 1.174271e+108 (Base 10) or 2e-360 to 2e360 (Base 2).

        

        

      PredefinedMetricSpecification -> (structure)

        

        A predefined metric.

        

        PredefinedMetricType -> (string)

          

          The metric type.

          

          

        ResourceLabel -> (string)

          

          Reserved for future use.

          

          

        

      CustomizedMetricSpecification -> (structure)

        

        Reserved for future use.

        

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

          

          

        

      ScaleOutCooldown -> (integer)

        

        The amount of time, in seconds, after a scale out activity completes before another scale out activity can start.

         

        While the cooldown period is in effect, the capacity that has been added by the previous scale out event that initiated the cooldown is calculated as part of the desired capacity for the next scale out. The intention is to continuously (but not excessively) scale out.

        

        

      ScaleInCooldown -> (integer)

        

        The amount of time, in seconds, after a scale in activity completes before another scale in activity can start.

         

        The cooldown period is used to block subsequent scale in requests until it has expired. The intention is to scale in conservatively to protect your application's availability. However, if another alarm triggers a scale out policy during the cooldown period after a scale-in, Application Auto Scaling scales out your scalable target immediately.

        

        

      

    Alarms -> (list)

      

      The CloudWatch alarms associated with the scaling policy.

      

      (structure)

        

        Represents a CloudWatch alarm associated with a scaling policy.

        

        AlarmName -> (string)

          

          The name of the alarm.

          

          

        AlarmARN -> (string)

          

          The Amazon Resource Name (ARN) of the alarm.

          

          

        

      

    CreationTime -> (timestamp)

      

      The Unix timestamp for when the scaling policy was created.

      

      

    

  

NextToken -> (string)

  

  The token required to get the next set of results. This value is ``null`` if there are no more results to return.

  

  

