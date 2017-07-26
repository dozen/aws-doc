[ :ref:`aws <cli:aws>` . :ref:`application-autoscaling <cli:aws application-autoscaling>` ]

.. _cli:aws application-autoscaling delete-scaling-policy:


*********************
delete-scaling-policy
*********************



===========
Description
===========



Deletes the specified Application Auto Scaling scaling policy.

 

Deleting a policy deletes the underlying alarm action, but does not delete the CloudWatch alarm associated with the scaling policy, even if it no longer has an associated action.

 

To create a scaling policy or update an existing one, see  put-scaling-policy .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/application-autoscaling-2016-02-06/DeleteScalingPolicy>`_


========
Synopsis
========

::

    delete-scaling-policy
  --policy-name <value>
  --service-namespace <value>
  --resource-id <value>
  --scalable-dimension <value>
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


  The identifier of the resource associated with the scalable target. This string consists of the resource type and unique identifier.

   

   
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

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a scaling policy**

This example deletes a scaling policy for the Amazon ECS service `web-app` running in the `default` cluster.

Command::

  aws application-autoscaling delete-scaling-policy --policy-name web-app-cpu-lt-25 --scalable-dimension ecs:service:DesiredCount --resource-id service/default/web-app --service-namespace ecs


======
Output
======

