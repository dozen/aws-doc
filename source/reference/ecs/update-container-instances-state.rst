[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs update-container-instances-state:


********************************
update-container-instances-state
********************************



===========
Description
===========



Modifies the status of an Amazon ECS container instance.

 

You can change the status of a container instance to ``DRAINING`` to manually remove an instance from a cluster, for example to perform system updates, update the Docker daemon, or scale down the cluster size. 

 

When you set a container instance to ``DRAINING`` , Amazon ECS prevents new tasks from being scheduled for placement on the container instance and replacement service tasks are started on other container instances in the cluster if the resources are available. Service tasks on the container instance that are in the ``PENDING`` state are stopped immediately.

 

Service tasks on the container instance that are in the ``RUNNING`` state are stopped and replaced according the service's deployment configuration parameters, ``minimumHealthyPercent`` and ``maximumPercent`` . Note that you can change the deployment configuration of your service using  update-service .

 

 
* If ``minimumHealthyPercent`` is below 100%, the scheduler can ignore ``desiredCount`` temporarily during task replacement. For example, ``desiredCount`` is four tasks, a minimum of 50% allows the scheduler to stop two existing tasks before starting two new tasks. If the minimum is 100%, the service scheduler can't remove existing tasks until the replacement tasks are considered healthy. Tasks for services that do not use a load balancer are considered healthy if they are in the ``RUNNING`` state. Tasks for services that use a load balancer are considered healthy if they are in the ``RUNNING`` state and the container instance they are hosted on is reported as healthy by the load balancer. 
 
* The ``maximumPercent`` parameter represents an upper limit on the number of running tasks during task replacement, which enables you to define the replacement batch size. For example, if ``desiredCount`` of four tasks, a maximum of 200% starts four new tasks before stopping the four tasks to be drained (provided that the cluster resources required to do this are available). If the maximum is 100%, then replacement tasks can't start until the draining tasks have stopped. 
 

 

Any ``PENDING`` or ``RUNNING`` tasks that do not belong to a service are not affected; you must wait for them to finish or stop them manually.

 

A container instance has completed draining when it has no more ``RUNNING`` tasks. You can verify this using  list-tasks .

 

When you set a container instance to ``ACTIVE`` , the Amazon ECS scheduler can begin scheduling tasks on the instance again.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/UpdateContainerInstancesState>`_


========
Synopsis
========

::

    update-container-instances-state
  [--cluster <value>]
  --container-instances <value>
  --status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container instance to update. If you do not specify a cluster, the default cluster is assumed.

  

``--container-instances`` (list)


  A list of container instance IDs or full Amazon Resource Name (ARN) entries.

  



Syntax::

  "string" "string" ...



``--status`` (string)


  The container instance state with which to update the container instance.

  

  Possible values:

  
  *   ``ACTIVE``

  
  *   ``DRAINING``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

containerInstances -> (list)

  

  The list of container instances.

  

  (structure)

    

    An EC2 instance that is running the Amazon ECS agent and has been registered with a cluster.

    

    containerInstanceArn -> (string)

      

      The Amazon Resource Name (ARN) of the container instance. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, ``arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* `` .

      

      

    ec2InstanceId -> (string)

      

      The EC2 instance ID of the container instance.

      

      

    version -> (long)

      

      The version counter for the container instance. Every time a container instance experiences a change that triggers a CloudWatch event, the version counter is incremented. If you are replicating your Amazon ECS container instance state with CloudWatch events, you can compare the version of a container instance reported by the Amazon ECS APIs with the version reported in CloudWatch events for the container instance (inside the ``detail`` object) to verify that the version in your event stream is current.

      

      

    versionInfo -> (structure)

      

      The version information for the Amazon ECS container agent and Docker daemon running on the container instance.

      

      agentVersion -> (string)

        

        The version number of the Amazon ECS container agent.

        

        

      agentHash -> (string)

        

        The Git commit hash for the Amazon ECS container agent build on the `amazon-ecs-agent <https://github.com/aws/amazon-ecs-agent/commits/master>`_ GitHub repository.

        

        

      dockerVersion -> (string)

        

        The Docker version running on the container instance.

        

        

      

    remainingResources -> (list)

      

      For most resource types, this parameter describes the remaining resources of the container instance that are available for new tasks. For port resource types, this parameter describes the ports that are reserved by the Amazon ECS container agent and any containers that have reserved port mappings; any port that is not specified here is available for new tasks.

      

      (structure)

        

        Describes the resources available for a container instance.

        

        name -> (string)

          

          The name of the resource, such as ``cpu`` , ``memory`` , ``ports`` , or a user-defined resource.

          

          

        type -> (string)

          

          The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

          

          

        doubleValue -> (double)

          

          When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

          

          

        longValue -> (long)

          

          When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

          

          

        integerValue -> (integer)

          

          When the ``integerValue`` type is set, the value of the resource must be an integer.

          

          

        stringSetValue -> (list)

          

          When the ``stringSetValue`` type is set, the value of the resource must be a string type.

          

          (string)

            

            

          

        

      

    registeredResources -> (list)

      

      For most resource types, this parameter describes the registered resources on the container instance that are in use by current tasks. For port resource types, this parameter describes the ports that were reserved by the Amazon ECS container agent when it registered the container instance with Amazon ECS.

      

      (structure)

        

        Describes the resources available for a container instance.

        

        name -> (string)

          

          The name of the resource, such as ``cpu`` , ``memory`` , ``ports`` , or a user-defined resource.

          

          

        type -> (string)

          

          The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

          

          

        doubleValue -> (double)

          

          When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

          

          

        longValue -> (long)

          

          When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

          

          

        integerValue -> (integer)

          

          When the ``integerValue`` type is set, the value of the resource must be an integer.

          

          

        stringSetValue -> (list)

          

          When the ``stringSetValue`` type is set, the value of the resource must be a string type.

          

          (string)

            

            

          

        

      

    status -> (string)

      

      The status of the container instance. The valid values are ``ACTIVE`` , ``INACTIVE`` , or ``DRAINING`` . ``ACTIVE`` indicates that the container instance can accept tasks. ``DRAINING`` indicates that new tasks are not placed on the container instance and any service tasks running on the container instance are removed if possible. For more information, see `Container Instance Draining <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/container-instance-draining.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

      

      

    agentConnected -> (boolean)

      

      This parameter returns ``true`` if the agent is actually connected to Amazon ECS. Registered instances with an agent that may be unhealthy or stopped return ``false`` , and instances without a connected agent cannot accept placement requests.

      

      

    runningTasksCount -> (integer)

      

      The number of tasks on the container instance that are in the ``RUNNING`` status.

      

      

    pendingTasksCount -> (integer)

      

      The number of tasks on the container instance that are in the ``PENDING`` status.

      

      

    agentUpdateStatus -> (string)

      

      The status of the most recent agent update. If an update has never been requested, this value is ``NULL`` .

      

      

    attributes -> (list)

      

      The attributes set for the container instance, either by the Amazon ECS container agent at instance registration or manually with the  put-attributes operation.

      

      (structure)

        

        An attribute is a name-value pair associated with an Amazon ECS object. Attributes enable you to extend the Amazon ECS data model by adding custom metadata to your resources. For more information, see `Attributes <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-constraints.html#attributes>`_ in the *Amazon EC2 Container Service Developer Guide* .

        

        name -> (string)

          

          The name of the attribute. Up to 128 letters (uppercase and lowercase), numbers, hyphens, underscores, and periods are allowed.

          

          

        value -> (string)

          

          The value of the attribute. Up to 128 letters (uppercase and lowercase), numbers, hyphens, underscores, periods, at signs (@), forward slashes, colons, and spaces are allowed.

          

          

        targetType -> (string)

          

          The type of the target with which to attach the attribute. This parameter is required if you use the short form ID for a resource instead of the full Amazon Resource Name (ARN).

          

          

        targetId -> (string)

          

          The ID of the target. You can specify the short form ID for a resource or the full Amazon Resource Name (ARN).

          

          

        

      

    registeredAt -> (timestamp)

      

      The Unix timestamp for when the container instance was registered.

      

      

    

  

failures -> (list)

  

  Any failures associated with the call.

  

  (structure)

    

    A failed resource.

    

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the failed resource.

      

      

    reason -> (string)

      

      The reason for the failure.

      

      

    

  

