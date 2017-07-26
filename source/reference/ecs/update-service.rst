[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs update-service:


**************
update-service
**************



===========
Description
===========



Modifies the desired count, deployment configuration, or task definition used in a service.

 

You can add to or subtract from the number of instantiations of a task definition in a service by specifying the cluster that the service is running in and a new ``desiredCount`` parameter.

 

You can use  update-service to modify your task definition and deploy a new version of your service.

 

You can also update the deployment configuration of a service. When a deployment is triggered by updating the task definition of a service, the service scheduler uses the deployment configuration parameters, ``minimumHealthyPercent`` and ``maximumPercent`` , to determine the deployment strategy.

 

 
* If ``minimumHealthyPercent`` is below 100%, the scheduler can ignore ``desiredCount`` temporarily during a deployment. For example, if ``desiredCount`` is four tasks, a minimum of 50% allows the scheduler to stop two existing tasks before starting two new tasks. Tasks for services that do not use a load balancer are considered healthy if they are in the ``RUNNING`` state. Tasks for services that use a load balancer are considered healthy if they are in the ``RUNNING`` state and the container instance they are hosted on is reported as healthy by the load balancer. 
 
* The ``maximumPercent`` parameter represents an upper limit on the number of running tasks during a deployment, which enables you to define the deployment batch size. For example, if ``desiredCount`` is four tasks, a maximum of 200% starts four new tasks before stopping the four older tasks (provided that the cluster resources required to do this are available). 
 

 

When  update-service stops a task during a deployment, the equivalent of ``docker stop`` is issued to the containers running in the task. This results in a ``SIGTERM`` and a 30-second timeout, after which ``SIGKILL`` is sent and the containers are forcibly stopped. If the container handles the ``SIGTERM`` gracefully and exits within 30 seconds from receiving it, no ``SIGKILL`` is sent.

 

When the service scheduler launches new tasks, it determines task placement in your cluster with the following logic:

 

 
* Determine which of the container instances in your cluster can support your service's task definition (for example, they have the required CPU, memory, ports, and container instance attributes). 
 
* By default, the service scheduler attempts to balance tasks across Availability Zones in this manner (although you can choose a different placement strategy): 

   
  * Sort the valid container instances by the fewest number of running tasks for this service in the same Availability Zone as the instance. For example, if zone A has one running service task and zones B and C each have zero, valid container instances in either zone B or C are considered optimal for placement. 
   
  * Place the new service task on a valid container instance in an optimal Availability Zone (based on the previous steps), favoring container instances with the fewest number of running tasks for this service. 
   

 
 

 

When the service scheduler stops running tasks, it attempts to maintain balance across the Availability Zones in your cluster using the following logic: 

 

 
* Sort the container instances by the largest number of running tasks for this service in the same Availability Zone as the instance. For example, if zone A has one running service task and zones B and C each have two, container instances in either zone B or C are considered optimal for termination. 
 
* Stop the task on a container instance in an optimal Availability Zone (based on the previous steps), favoring container instances with the largest number of running tasks for this service. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/UpdateService>`_


========
Synopsis
========

::

    update-service
  [--cluster <value>]
  --service <value>
  [--desired-count <value>]
  [--task-definition <value>]
  [--deployment-configuration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that your service is running on. If you do not specify a cluster, the default cluster is assumed.

  

``--service`` (string)


  The name of the service to update.

  

``--desired-count`` (integer)


  The number of instantiations of the task to place and keep running in your service.

  

``--task-definition`` (string)


  The ``family`` and ``revision`` (``family:revision`` ) or full Amazon Resource Name (ARN) of the task definition to run in your service. If a ``revision`` is not specified, the latest ``ACTIVE`` revision is used. If you modify the task definition with ``update-service`` , Amazon ECS spawns a task with the new version of the task definition and then stops an old task after the new version is running.

  

``--deployment-configuration`` (structure)


  Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks.

  



Shorthand Syntax::

    maximumPercent=integer,minimumHealthyPercent=integer




JSON Syntax::

  {
    "maximumPercent": integer,
    "minimumHealthyPercent": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change the task definition used in a service**

This example command updates the ``my-http-service`` service to use the ``amazon-ecs-sample`` task definition. 

Command::

  aws ecs update-service --service my-http-service --task-definition amazon-ecs-sample

**To change the number of tasks in a service**

This example command updates the desired count of the ``my-http-service`` service to 10. 

Command::

  aws ecs update-service --service my-http-service --desired-count 10

======
Output
======

service -> (structure)

  

  The full description of your service following the update call.

  

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

        

        

      

    

  

