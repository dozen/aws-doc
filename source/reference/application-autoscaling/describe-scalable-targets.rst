[ :ref:`aws <cli:aws>` . :ref:`application-autoscaling <cli:aws application-autoscaling>` ]

.. _cli:aws application-autoscaling describe-scalable-targets:


*************************
describe-scalable-targets
*************************



===========
Description
===========



Provides descriptive information about the scalable targets in the specified namespace.

 

You can filter the results using the ``ResourceIds`` and ``scalable-dimension`` parameters.

 

To create a scalable target or update an existing one, see  register-scalable-target . If you are no longer using a scalable target, you can deregister it using  deregister-scalable-target .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/application-autoscaling-2016-02-06/DescribeScalableTargets>`_


``describe-scalable-targets`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ScalableTargets``


========
Synopsis
========

::

    describe-scalable-targets
  --service-namespace <value>
  [--resource-ids <value>]
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

  

  

``--resource-ids`` (list)


  The identifier of the resource associated with the scalable target. This string consists of the resource type and unique identifier. If you specify a scalable dimension, you must also specify a resource ID.

   

   
  * ECS service - The resource type is ``service`` and the unique identifier is the cluster name and service name. Example: ``service/default/sample-webapp`` . 
   
  * Spot fleet request - The resource type is ``spot-fleet-request`` and the unique identifier is the Spot fleet request ID. Example: ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` . 
   
  * EMR cluster - The resource type is ``instancegroup`` and the unique identifier is the cluster ID and instance group ID. Example: ``instancegroup/j-2EEZNYKUA1NTV/ig-1791Y4E1L8YI0`` . 
   
  * AppStream 2.0 fleet - The resource type is ``fleet`` and the unique identifier is the fleet name. Example: ``fleet/sample-fleet`` . 
   
  * DynamoDB table - The resource type is ``table`` and the unique identifier is the resource ID. Example: ``table/my-table`` . 
   
  * DynamoDB global secondary index - The resource type is ``index`` and the unique identifier is the resource ID. Example: ``table/my-table/index/my-table-index`` . 
   

  



Syntax::

  "string" "string" ...



``--scalable-dimension`` (string)


  The scalable dimension associated with the scalable target. This string consists of the service namespace, resource type, and scaling property. If you specify a scalable dimension, you must also specify a resource ID.

   

   
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

**To describe scalable targets**

This example command describes the scalable targets for the `ecs` service namespace.

Command::

  aws application-autoscaling describe-scalable-targets --service-namespace ecs

Output::

	{
	    "ScalableTargets": [
	        {
	            "ScalableDimension": "ecs:service:DesiredCount",
	            "ResourceId": "service/default/web-app",
	            "RoleARN": "arn:aws:iam::012345678910:role/ApplicationAutoscalingECSRole",
	            "CreationTime": 1462558906.199,
	            "MinCapacity": 1,
	            "ServiceNamespace": "ecs",
	            "MaxCapacity": 10
	        }
	    ]
	}


======
Output
======

ScalableTargets -> (list)

  

  The list of scalable targets that matches the request parameters.

  

  (structure)

    

    Represents a scalable target.

    

    ServiceNamespace -> (string)

      

      The namespace of the AWS service. For more information, see `AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#genref-aws-service-namespaces>`_ in the *Amazon Web Services General Reference* .

      

      

    ResourceId -> (string)

      

      The identifier of the resource associated with the scalable target. This string consists of the resource type and unique identifier.

       

       
      * ECS service - The resource type is ``service`` and the unique identifier is the cluster name and service name. Example: ``service/default/sample-webapp`` . 
       
      * Spot fleet request - The resource type is ``spot-fleet-request`` and the unique identifier is the Spot fleet request ID. Example: ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` . 
       
      * EMR cluster - The resource type is ``instancegroup`` and the unique identifier is the cluster ID and instance group ID. Example: ``instancegroup/j-2EEZNYKUA1NTV/ig-1791Y4E1L8YI0`` . 
       
      * AppStream 2.0 fleet - The resource type is ``fleet`` and the unique identifier is the fleet name. Example: ``fleet/sample-fleet`` . 
       
      * DynamoDB table - The resource type is ``table`` and the unique identifier is the resource ID. Example: ``table/my-table`` . 
       
      * DynamoDB global secondary index - The resource type is ``index`` and the unique identifier is the resource ID. Example: ``table/my-table/index/my-table-index`` . 
       

      

      

    ScalableDimension -> (string)

      

      The scalable dimension associated with the scalable target. This string consists of the service namespace, resource type, and scaling property.

       

       
      * ``ecs:service:DesiredCount`` - The desired task count of an ECS service. 
       
      * ``ec2:spot-fleet-request:TargetCapacity`` - The target capacity of a Spot fleet request. 
       
      * ``elasticmapreduce:instancegroup:InstanceCount`` - The instance count of an EMR Instance Group. 
       
      * ``appstream:fleet:DesiredCapacity`` - The desired capacity of an AppStream 2.0 fleet. 
       
      * ``dynamodb:table:ReadCapacityUnits`` - The provisioned read capacity for a DynamoDB table. 
       
      * ``dynamodb:table:WriteCapacityUnits`` - The provisioned write capacity for a DynamoDB table. 
       
      * ``dynamodb:index:ReadCapacityUnits`` - The provisioned read capacity for a DynamoDB global secondary index. 
       
      * ``dynamodb:index:WriteCapacityUnits`` - The provisioned write capacity for a DynamoDB global secondary index. 
       

      

      

    MinCapacity -> (integer)

      

      The minimum value to scale to in response to a scale in event.

      

      

    MaxCapacity -> (integer)

      

      The maximum value to scale to in response to a scale out event.

      

      

    RoleARN -> (string)

      

      The ARN of an IAM role that allows Application Auto Scaling to modify the scalable target on your behalf.

      

      

    CreationTime -> (timestamp)

      

      The Unix timestamp for when the scalable target was created.

      

      

    

  

NextToken -> (string)

  

  The token required to get the next set of results. This value is ``null`` if there are no more results to return.

  

  

