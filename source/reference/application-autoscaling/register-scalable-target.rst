[ :ref:`aws <cli:aws>` . :ref:`application-autoscaling <cli:aws application-autoscaling>` ]

.. _cli:aws application-autoscaling register-scalable-target:


************************
register-scalable-target
************************



===========
Description
===========



Registers or updates a scalable target. A scalable target is a resource that Application Auto Scaling can scale out or scale in. After you have registered a scalable target, you can use this operation to update the minimum and maximum values for your scalable dimension.

 

After you register a scalable target, you can create and apply scaling policies using  put-scaling-policy . You can view the scaling policies for a service namespace using  describe-scalable-targets . If you are no longer using a scalable target, you can deregister it using  deregister-scalable-target .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/application-autoscaling-2016-02-06/RegisterScalableTarget>`_


========
Synopsis
========

::

    register-scalable-target
  --service-namespace <value>
  --resource-id <value>
  --scalable-dimension <value>
  [--min-capacity <value>]
  [--max-capacity <value>]
  [--role-arn <value>]
  [--cli-input-json <value>]
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


  The identifier of the resource associated with the scalable target. This string consists of the resource type and unique identifier.

   

   
  * ECS service - The resource type is ``service`` and the unique identifier is the cluster name and service name. Example: ``service/default/sample-webapp`` . 
   
  * Spot fleet request - The resource type is ``spot-fleet-request`` and the unique identifier is the Spot fleet request ID. Example: ``spot-fleet-request/sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE`` . 
   
  * EMR cluster - The resource type is ``instancegroup`` and the unique identifier is the cluster ID and instance group ID. Example: ``instancegroup/j-2EEZNYKUA1NTV/ig-1791Y4E1L8YI0`` . 
   
  * AppStream 2.0 fleet - The resource type is ``fleet`` and the unique identifier is the fleet name. Example: ``fleet/sample-fleet`` . 
   
  * DynamoDB table - The resource type is ``table`` and the unique identifier is the resource ID. Example: ``table/my-table`` . 
   
  * DynamoDB global secondary index - The resource type is ``index`` and the unique identifier is the resource ID. Example: ``table/my-table/index/my-table-index`` . 
   

  

``--scalable-dimension`` (string)


  The scalable dimension associated with the scalable target. This string consists of the service namespace, resource type, and scaling property.

   

   
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

  

  

``--min-capacity`` (integer)


  The minimum value to scale to in response to a scale in event. This parameter is required if you are registering a scalable target and optional if you are updating one.

  

``--max-capacity`` (integer)


  The maximum value to scale to in response to a scale out event. This parameter is required if you are registering a scalable target and optional if you are updating one.

  

``--role-arn`` (string)


  The ARN of an IAM role that allows Application Auto Scaling to modify the scalable target on your behalf. This parameter is required when you register a scalable target and optional when you update one.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To register a new scalable target**

This example command registers a scalable target from an Amazon ECS service called `web-app` that is running on the `default` cluster, with a minimum desired count of 1 task and a maximum desired count of 10 tasks.

Command::

  aws application-autoscaling register-scalable-target --resource-id service/default/web-app --service-namespace ecs --scalable-dimension ecs:service:DesiredCount --min-capacity 1 --max-capacity 10 --role-arn arn:aws:iam::012345678910:role/ApplicationAutoscalingECSRole

Output::

	{
	    "cluster": {
	        "status": "ACTIVE",
	        "clusterName": "my_cluster",
	        "registeredContainerInstancesCount": 0,
	        "pendingTasksCount": 0,
	        "runningTasksCount": 0,
	        "activeServicesCount": 0,
	        "clusterArn": "arn:aws:ecs:<region>:<aws_account_id>:cluster/my_cluster"
	    }
	}


======
Output
======

