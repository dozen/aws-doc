[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs deregister-container-instance:


*****************************
deregister-container-instance
*****************************



===========
Description
===========



Deregisters an Amazon ECS container instance from the specified cluster. This instance is no longer available to run tasks.

 

If you intend to use the container instance for some other purpose after deregistration, you should stop all of the tasks running on the container instance before deregistration to avoid any orphaned tasks from consuming resources.

 

Deregistering a container instance removes the instance from a cluster, but it does not terminate the EC2 instance; if you are finished using the instance, be sure to terminate it in the Amazon EC2 console to stop billing.

 

.. note::

   

  If you terminate a running container instance, Amazon ECS automatically deregisters the instance from your cluster (stopped container instances or instances with disconnected agents are not automatically deregistered when terminated).

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/DeregisterContainerInstance>`_


========
Synopsis
========

::

    deregister-container-instance
  [--cluster <value>]
  --container-instance <value>
  [--force | --no-force]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container instance to deregister. If you do not specify a cluster, the default cluster is assumed.

  

``--container-instance`` (string)


  The container instance ID or full Amazon Resource Name (ARN) of the container instance to deregister. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, ``arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* `` .

  

``--force`` | ``--no-force`` (boolean)


  Forces the deregistration of the container instance. If you have tasks running on the container instance when you deregister it with the ``force`` option, these tasks remain running until you terminate the instance or the tasks stop through some other means, but they are orphaned (no longer monitored or accounted for by Amazon ECS). If an orphaned task on your container instance is part of an Amazon ECS service, then the service scheduler starts another copy of that task, on a different container instance if possible. 

   

  Any containers in orphaned service tasks that are registered with a Classic load balancer or an Application load balancer target group are deregistered, and they will begin connection draining according to the settings on the load balancer or target group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To deregister a container instance from a cluster**

This example deregisters a container instance from the specified cluster in your default region. If there are still tasks running on the container instance, you must either stop those tasks before deregistering, or use the force option.

Command::

  aws ecs deregister-container-instance --cluster default --container-instance <container_instance_UUID> --force

======
Output
======

containerInstance -> (structure)

  

  The container instance that was deregistered.

  

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

    

    

  

