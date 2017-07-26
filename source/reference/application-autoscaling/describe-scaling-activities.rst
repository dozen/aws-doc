[ :ref:`aws <cli:aws>` . :ref:`application-autoscaling <cli:aws application-autoscaling>` ]

.. _cli:aws application-autoscaling describe-scaling-activities:


***************************
describe-scaling-activities
***************************



===========
Description
===========



Provides descriptive information about the scaling activities in the specified namespace from the previous six weeks.

 

You can filter the results using the ``ResourceId`` and ``scalable-dimension`` parameters.

 

Scaling activities are triggered by CloudWatch alarms that are associated with scaling policies. To view the scaling policies for a service namespace, see  describe-scaling-policies . To create a scaling policy or update an existing one, see  put-scaling-policy .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/application-autoscaling-2016-02-06/DescribeScalingActivities>`_


``describe-scaling-activities`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ScalingActivities``


========
Synopsis
========

::

    describe-scaling-activities
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

``--service-namespace`` (string)


  The namespace of the AWS service. For more information, see `AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#genref-aws-service-namespaces>`_ in the *Amazon Web Services General Reference* .

  

  Possible values:

  
  *   ``ecs``

  
  *   ``elasticmapreduce``

  
  *   ``ec2``

  
  *   ``appstream``

  
  *   ``dynamodb``

  

  

``--resource-id`` (string)


  The identifier of the resource associated with the scaling activity. This string consists of the resource type and unique identifier. If you specify a scalable dimension, you must also specify a resource ID.

   

   
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

**To describe scaling activities for a scalable target**

This example describes the scaling activities for an Amazon ECS service called `web-app` that is running in the `default` cluster.

Command::

  aws application-autoscaling describe-scaling-activities --service-namespace ecs --scalable-dimension ecs:service:DesiredCount --resource-id service/default/web-app

Output::

  {
    "ScalingActivities": [
      {
        "ScalableDimension": "ecs:service:DesiredCount",
        "Description": "Setting desired count to 1.",
        "ResourceId": "service/default/web-app",
        "ActivityId": "e6c5f7d1-dbbb-4a3f-89b2-51f33e766399",
        "StartTime": 1462575838.171,
        "ServiceNamespace": "ecs",
        "EndTime": 1462575872.111,
        "Cause": "monitor alarm web-app-cpu-lt-25 in state ALARM triggered policy web-app-cpu-lt-25",
        "StatusMessage": "Successfully set desired count to 1. Change successfully fulfilled by ecs.",
        "StatusCode": "Successful"
      }
    ]
  }

======
Output
======

ScalingActivities -> (list)

  

  A list of scaling activity objects.

  

  (structure)

    

    Represents a scaling activity.

    

    ActivityId -> (string)

      

      The unique identifier of the scaling activity.

      

      

    ServiceNamespace -> (string)

      

      The namespace of the AWS service. For more information, see `AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#genref-aws-service-namespaces>`_ in the *Amazon Web Services General Reference* .

      

      

    ResourceId -> (string)

      

      The identifier of the resource associated with the scaling activity. This string consists of the resource type and unique identifier.

       

       
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
       

      

      

    Description -> (string)

      

      A simple description of what action the scaling activity intends to accomplish.

      

      

    Cause -> (string)

      

      A simple description of what caused the scaling activity to happen.

      

      

    StartTime -> (timestamp)

      

      The Unix timestamp for when the scaling activity began.

      

      

    EndTime -> (timestamp)

      

      The Unix timestamp for when the scaling activity ended.

      

      

    StatusCode -> (string)

      

      Indicates the status of the scaling activity.

      

      

    StatusMessage -> (string)

      

      A simple message about the current status of the scaling activity.

      

      

    Details -> (string)

      

      The details about the scaling activity.

      

      

    

  

NextToken -> (string)

  

  The token required to get the next set of results. This value is ``null`` if there are no more results to return.

  

  

