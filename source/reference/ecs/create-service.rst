[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs create-service:


**************
create-service
**************



===========
Description
===========



Runs and maintains a desired number of tasks from a specified task definition. If the number of tasks running in a service drops below ``desiredCount`` , Amazon ECS spawns another copy of the task in the specified cluster. To update an existing service, see  update-service .

 

In addition to maintaining the desired count of tasks in your service, you can optionally run your service behind a load balancer. The load balancer distributes traffic across the tasks that are associated with the service. For more information, see `Service Load Balancing <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-load-balancing.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

 

You can optionally specify a deployment configuration for your service. During a deployment (which is triggered by changing the task definition or the desired count of a service with an  update-service operation), the service scheduler uses the ``minimumHealthyPercent`` and ``maximumPercent`` parameters to determine the deployment strategy.

 

The ``minimumHealthyPercent`` represents a lower limit on the number of your service's tasks that must remain in the ``RUNNING`` state during a deployment, as a percentage of the ``desiredCount`` (rounded up to the nearest integer). This parameter enables you to deploy without using additional cluster capacity. For example, if your service has a ``desiredCount`` of four tasks and a ``minimumHealthyPercent`` of 50%, the scheduler can stop two existing tasks to free up cluster capacity before starting two new tasks. Tasks for services that *do not* use a load balancer are considered healthy if they are in the ``RUNNING`` state. Tasks for services that *do* use a load balancer are considered healthy if they are in the ``RUNNING`` state and the container instance they are hosted on is reported as healthy by the load balancer. The default value for ``minimumHealthyPercent`` is 50% in the console and 100% for the AWS CLI, the AWS SDKs, and the APIs.

 

The ``maximumPercent`` parameter represents an upper limit on the number of your service's tasks that are allowed in the ``RUNNING`` or ``PENDING`` state during a deployment, as a percentage of the ``desiredCount`` (rounded down to the nearest integer). This parameter enables you to define the deployment batch size. For example, if your service has a ``desiredCount`` of four tasks and a ``maximumPercent`` value of 200%, the scheduler can start four new tasks before stopping the four older tasks (provided that the cluster resources required to do this are available). The default value for ``maximumPercent`` is 200%.

 

When the service scheduler launches new tasks, it determines task placement in your cluster using the following logic:

 

 
* Determine which of the container instances in your cluster can support your service's task definition (for example, they have the required CPU, memory, ports, and container instance attributes). 
 
* By default, the service scheduler attempts to balance tasks across Availability Zones in this manner (although you can choose a different placement strategy) with the ``placementStrategy`` parameter): 

   
  * Sort the valid container instances by the fewest number of running tasks for this service in the same Availability Zone as the instance. For example, if zone A has one running service task and zones B and C each have zero, valid container instances in either zone B or C are considered optimal for placement. 
   
  * Place the new service task on a valid container instance in an optimal Availability Zone (based on the previous steps), favoring container instances with the fewest number of running tasks for this service. 
   

 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/CreateService>`_


========
Synopsis
========

::

    create-service
  [--cluster <value>]
  --service-name <value>
  --task-definition <value>
  [--load-balancers <value>]
  --desired-count <value>
  [--client-token <value>]
  [--role <value>]
  [--deployment-configuration <value>]
  [--placement-constraints <value>]
  [--placement-strategy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster on which to run your service. If you do not specify a cluster, the default cluster is assumed.

  

``--service-name`` (string)


  The name of your service. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. Service names must be unique within a cluster, but you can have similarly named services in multiple clusters within a region or across multiple regions.

  

``--task-definition`` (string)


  The ``family`` and ``revision`` (``family:revision`` ) or full Amazon Resource Name (ARN) of the task definition to run in your service. If a ``revision`` is not specified, the latest ``ACTIVE`` revision is used.

  

``--load-balancers`` (list)


  A load balancer object representing the load balancer to use with your service. Currently, you are limited to one load balancer or target group per service. After you create a service, the load balancer name or target group ARN, container name, and container port specified in the service definition are immutable.

   

  For Elastic Load Balancing Classic load balancers, this object must contain the load balancer name, the container name (as it appears in a container definition), and the container port to access from the load balancer. When a task from this service is placed on a container instance, the container instance is registered with the load balancer specified here.

   

  For Elastic Load Balancing Application load balancers, this object must contain the load balancer target group ARN, the container name (as it appears in a container definition), and the container port to access from the load balancer. When a task from this service is placed on a container instance, the container instance and port combination is registered as a target in the target group specified here.

  



Shorthand Syntax::

    targetGroupArn=string,loadBalancerName=string,containerName=string,containerPort=integer ...




JSON Syntax::

  [
    {
      "targetGroupArn": "string",
      "loadBalancerName": "string",
      "containerName": "string",
      "containerPort": integer
    }
    ...
  ]



``--desired-count`` (integer)


  The number of instantiations of the specified task definition to place and keep running on your cluster.

  

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure the idempotency of the request. Up to 32 ASCII characters are allowed.

  

``--role`` (string)


  The name or full Amazon Resource Name (ARN) of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service. If you specify the ``role`` parameter, you must also specify a load balancer object with the ``loadBalancers`` parameter.

   

  If your specified role has a path other than ``/`` , then you must either specify the full role ARN (this is recommended) or prefix the role name with the path. For example, if a role with the name ``bar`` has a path of ``/foo/`` then you would specify ``/foo/bar`` as the role name. For more information, see `Friendly Names and Paths <http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html#identifiers-friendly-names>`_ in the *IAM User Guide* .

  

``--deployment-configuration`` (structure)


  Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks.

  



Shorthand Syntax::

    maximumPercent=integer,minimumHealthyPercent=integer




JSON Syntax::

  {
    "maximumPercent": integer,
    "minimumHealthyPercent": integer
  }



``--placement-constraints`` (list)


  An array of placement constraint objects to use for tasks in your service. You can specify a maximum of 10 constraints per task (this limit includes constraints in the task definition and those specified at run time). 

  



Shorthand Syntax::

    type=string,expression=string ...




JSON Syntax::

  [
    {
      "type": "distinctInstance"|"memberOf",
      "expression": "string"
    }
    ...
  ]



``--placement-strategy`` (list)


  The placement strategy objects to use for tasks in your service. You can specify a maximum of 5 strategy rules per service.

  



Shorthand Syntax::

    type=string,field=string ...




JSON Syntax::

  [
    {
      "type": "random"|"spread"|"binpack",
      "field": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a new service**

This example command creates a service in your default region called ``ecs-simple-service``. The service uses the ``ecs-demo`` task definition and it maintains 10 instantiations of that task.

Command::

  aws ecs create-service --service-name ecs-simple-service --task-definition ecs-demo --desired-count 10

Output::

	{
	    "service": {
	        "status": "ACTIVE",
	        "taskDefinition": "arn:aws:ecs:<region>:<aws_account_id>:task-definition/ecs-demo:1",
	        "pendingCount": 0,
	        "loadBalancers": [],
	        "desiredCount": 10,
	        "serviceName": "ecs-simple-service",
	        "clusterArn": "arn:aws:ecs:<region>:<aws_account_id>:cluster/default",
	        "serviceArn": "arn:aws:ecs:<region>:<aws_account_id>:service/ecs-simple-service",
	        "deployments": [
	            {
	                "status": "PRIMARY",
	                "pendingCount": 0,
	                "createdAt": 1428096748.604,
	                "desiredCount": 10,
	                "taskDefinition": "arn:aws:ecs:<region>:<aws_account_id>:task-definition/ecs-demo:1",
	                "updatedAt": 1428096748.604,
	                "id": "ecs-svc/<deployment_id>",
	                "runningCount": 0
	            }
	        ],
	        "events": [],
	        "runningCount": 0
	    }
	}

	
**To create a new service behind a load balancer**

This example command creates a service in your default region called ``ecs-simple-service-elb``. The service uses the ``ecs-demo`` task definition and it maintains 10 instantiations of that task. You must have a load balancer configured in the same region as your container instances.

This example uses the ``--cli-input-json`` option and a JSON input file called ``ecs-simple-service-elb.json`` with the below format.

Input file::

    {
        "serviceName": "ecs-simple-service-elb",
        "taskDefinition": "ecs-demo",
        "loadBalancers": [
            {
                "loadBalancerName": "EC2Contai-EcsElast-S06278JGSJCM",
                "containerName": "simple-demo",
                "containerPort": 80
            }
        ],
        "desiredCount": 10,
        "role": "ecsServiceRole"
    }

Command::

  aws ecs create-service --service-name ecs-simple-service-elb --cli-input-json file://ecs-simple-service-elb.json

Output::

	{
	    "service": {
	        "status": "ACTIVE",
	        "taskDefinition": "arn:aws:ecs:<region>:<aws_account_id>:task-definition/ecs-demo:1",
	        "pendingCount": 0,
	        "loadBalancers": [
	            {
	                "containerName": "ecs-demo",
	                "containerPort": 80,
	                "loadBalancerName": "EC2Contai-EcsElast-S06278JGSJCM"
	            }
	        ],
	        "roleArn": "arn:aws:iam::<aws_account_id>:role/ecsServiceRole",
	        "desiredCount": 10,
	        "serviceName": "ecs-simple-service-elb",
	        "clusterArn": "arn:aws:ecs:<region>:<aws_account_id>:cluster/default",
	        "serviceArn": "arn:aws:ecs:<region>:<aws_account_id>:service/ecs-simple-service-elb",
	        "deployments": [
	            {
	                "status": "PRIMARY",
	                "pendingCount": 0,
	                "createdAt": 1428100239.123,
	                "desiredCount": 10,
	                "taskDefinition": "arn:aws:ecs:<region>:<aws_account_id>:task-definition/ecs-demo:1",
	                "updatedAt": 1428100239.123,
	                "id": "ecs-svc/<deployment_id>",
	                "runningCount": 0
	            }
	        ],
	        "events": [],
	        "runningCount": 0
	    }
	}

======
Output
======

service -> (structure)

  

  The full description of your service following the create call.

  

  serviceArn -> (string)

    

    The Amazon Resource Name (ARN) that identifies the service. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the service, the AWS account ID of the service owner, the ``service`` namespace, and then the service name. For example, ``arn:aws:ecs:*region* :*012345678910* :service/*my-service* `` .

    

    

  serviceName -> (string)

    

    The name of your service. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. Service names must be unique within a cluster, but you can have similarly named services in multiple clusters within a region or across multiple regions.

    

    

  clusterArn -> (string)

    

    The Amazon Resource Name (ARN) of the cluster that hosts the service.

    

    

  loadBalancers -> (list)

    

    A list of Elastic Load Balancing load balancer objects, containing the load balancer name, the container name (as it appears in a container definition), and the container port to access from the load balancer.

    

    (structure)

      

      Details on a load balancer that is used with a service.

      

      targetGroupArn -> (string)

        

        The full Amazon Resource Name (ARN) of the Elastic Load Balancing target group associated with a service.

        

        

      loadBalancerName -> (string)

        

        The name of a Classic load balancer.

        

        

      containerName -> (string)

        

        The name of the container (as it appears in a container definition) to associate with the load balancer.

        

        

      containerPort -> (integer)

        

        The port on the container to associate with the load balancer. This port must correspond to a ``containerPort`` in the service's task definition. Your container instances must allow ingress traffic on the ``hostPort`` of the port mapping.

        

        

      

    

  status -> (string)

    

    The status of the service. The valid values are ``ACTIVE`` , ``DRAINING`` , or ``INACTIVE`` .

    

    

  desiredCount -> (integer)

    

    The desired number of instantiations of the task definition to keep running on the service. This value is specified when the service is created with  create-service , and it can be modified with  update-service .

    

    

  runningCount -> (integer)

    

    The number of tasks in the cluster that are in the ``RUNNING`` state.

    

    

  pendingCount -> (integer)

    

    The number of tasks in the cluster that are in the ``PENDING`` state.

    

    

  taskDefinition -> (string)

    

    The task definition to use for tasks in the service. This value is specified when the service is created with  create-service , and it can be modified with  update-service .

    

    

  deploymentConfiguration -> (structure)

    

    Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks.

    

    maximumPercent -> (integer)

      

      The upper limit (as a percentage of the service's ``desiredCount`` ) of the number of tasks that are allowed in the ``RUNNING`` or ``PENDING`` state in a service during a deployment. The maximum number of tasks during a deployment is the ``desiredCount`` multiplied by ``maximumPercent`` /100, rounded down to the nearest integer value.

      

      

    minimumHealthyPercent -> (integer)

      

      The lower limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that must remain in the ``RUNNING`` state in a service during a deployment. The minimum healthy tasks during a deployment is the ``desiredCount`` multiplied by ``minimumHealthyPercent`` /100, rounded up to the nearest integer value.

      

      

    

  deployments -> (list)

    

    The current state of deployments for the service.

    

    (structure)

      

      The details of an Amazon ECS service deployment.

      

      id -> (string)

        

        The ID of the deployment.

        

        

      status -> (string)

        

        The status of the deployment. Valid values are ``PRIMARY`` (for the most recent deployment), ``ACTIVE`` (for previous deployments that still have tasks running, but are being replaced with the ``PRIMARY`` deployment), and ``INACTIVE`` (for deployments that have been completely replaced).

        

        

      taskDefinition -> (string)

        

        The most recent task definition that was specified for the service to use.

        

        

      desiredCount -> (integer)

        

        The most recent desired count of tasks that was specified for the service to deploy or maintain.

        

        

      pendingCount -> (integer)

        

        The number of tasks in the deployment that are in the ``PENDING`` status.

        

        

      runningCount -> (integer)

        

        The number of tasks in the deployment that are in the ``RUNNING`` status.

        

        

      createdAt -> (timestamp)

        

        The Unix timestamp for when the service was created.

        

        

      updatedAt -> (timestamp)

        

        The Unix timestamp for when the service was last updated.

        

        

      

    

  roleArn -> (string)

    

    The Amazon Resource Name (ARN) of the IAM role associated with the service that allows the Amazon ECS container agent to register container instances with an Elastic Load Balancing load balancer.

    

    

  events -> (list)

    

    The event stream for your service. A maximum of 100 of the latest events are displayed.

    

    (structure)

      

      Details on an event associated with a service.

      

      id -> (string)

        

        The ID string of the event.

        

        

      createdAt -> (timestamp)

        

        The Unix timestamp for when the event was triggered.

        

        

      message -> (string)

        

        The event message.

        

        

      

    

  createdAt -> (timestamp)

    

    The Unix timestamp for when the service was created.

    

    

  placementConstraints -> (list)

    

    The placement constraints for the tasks in the service.

    

    (structure)

      

      An object representing a constraint on task placement. For more information, see `Task Placement Constraints <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-constraints.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

      

      type -> (string)

        

        The type of constraint. Use ``distinctInstance`` to ensure that each task in a particular group is running on a different container instance. Use ``memberOf`` to restrict selection to a group of valid candidates. Note that ``distinctInstance`` is not supported in task definitions.

        

        

      expression -> (string)

        

        A cluster query language expression to apply to the constraint. Note you cannot specify an expression if the constraint type is ``distinctInstance`` . For more information, see `Cluster Query Language <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/cluster-query-language.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

        

        

      

    

  placementStrategy -> (list)

    

    The placement strategy that determines how tasks for the service are placed.

    

    (structure)

      

      The task placement strategy for a task or service. For more information, see `Task Placement Strategies <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-strategies.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

      

      type -> (string)

        

        The type of placement strategy. The ``random`` placement strategy randomly places tasks on available candidates. The ``spread`` placement strategy spreads placement across available candidates evenly based on the ``field`` parameter. The ``binpack`` strategy places tasks on available candidates that have the least available amount of the resource that is specified with the ``field`` parameter. For example, if you binpack on memory, a task is placed on the instance with the least amount of remaining memory (but still enough to run the task).

        

        

      field -> (string)

        

        The field to apply the placement strategy against. For the ``spread`` placement strategy, valid values are ``instanceId`` (or ``host`` , which has the same effect), or any platform or custom attribute that is applied to a container instance, such as ``attribute:ecs.availability-zone`` . For the ``binpack`` placement strategy, valid values are ``cpu`` and ``memory`` . For the ``random`` placement strategy, this field is not used.

        

        

      

    

  

