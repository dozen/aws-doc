[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs update-container-agent:


**********************
update-container-agent
**********************



===========
Description
===========



Updates the Amazon ECS container agent on a specified container instance. Updating the Amazon ECS container agent does not interrupt running tasks or services on the container instance. The process for updating the agent differs depending on whether your container instance was launched with the Amazon ECS-optimized AMI or another operating system.

 

``update-container-agent`` requires the Amazon ECS-optimized AMI or Amazon Linux with the ``ecs-init`` service installed and running. For help updating the Amazon ECS container agent on other operating systems, see `Manually Updating the Amazon ECS Container Agent`_ in the *Amazon EC2 Container Service Developer Guide* .



========
Synopsis
========

::

    update-container-agent
  [--cluster <value>]
  --container-instance <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that your container instance is running on. If you do not specify a cluster, the default cluster is assumed.

  

``--container-instance`` (string)


  The container instance ID or full Amazon Resource Name (ARN) entries for the container instance on which you would like to update the Amazon ECS container agent.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To update the container agent on an Amazon ECS container instance**

This example command updates the container agent on the container instance ``a3e98c65-2a40-4452-a63c-62beb4d9be9b`` in the default cluster. 

Command::

  aws ecs update-container-agent --cluster default --container-instance a3e98c65-2a40-4452-a63c-62beb4d9be9b

Output::

  {
      "containerInstance": {
          "status": "ACTIVE",
  ...
          "agentUpdateStatus": "PENDING",
          "versionInfo": {
              "agentVersion": "1.0.0",
              "agentHash": "4023248",
              "dockerVersion": "DockerVersion: 1.5.0"
          }
      }
  }

======
Output
======

containerInstance -> (structure)

  

  An EC2 instance that is running the Amazon ECS agent and has been registered with a cluster.

  

  containerInstanceArn -> (string)

    

    The Amazon Resource Name (ARN) of the container instance. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* .

    

    

  ec2InstanceId -> (string)

    

    The EC2 instance ID of the container instance.

    

    

  versionInfo -> (structure)

    

    The version information for the Amazon ECS container agent and Docker daemon running on the container instance.

    

    agentVersion -> (string)

      

      The version number of the Amazon ECS container agent.

      

      

    agentHash -> (string)

      

      The Git commit hash for the Amazon ECS container agent build on the `amazon-ecs-agent`_ GitHub repository.

      

      

    dockerVersion -> (string)

      

      The Docker version running on the container instance.

      

      

    

  remainingResources -> (list)

    

    The remaining resources of the container instance that are available for new tasks.

    

    (structure)

      

      Describes the resources available for a container instance.

      

      name -> (string)

        

        The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

        

        

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

    

    The registered resources on the container instance that are in use by current tasks.

    

    (structure)

      

      Describes the resources available for a container instance.

      

      name -> (string)

        

        The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

        

        

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

    

    The status of the container instance. The valid values are ``ACTIVE`` or ``INACTIVE`` . ``ACTIVE`` indicates that the container instance can accept tasks.

    

    

  agentConnected -> (boolean)

    

    This parameter returns ``true`` if the agent is actually connected to Amazon ECS. Registered instances with an agent that may be unhealthy or stopped return ``false`` , and instances without a connected agent cannot accept placement requests.

    

    

  runningTasksCount -> (integer)

    

    The number of tasks on the container instance that are in the ``RUNNING`` status.

    

    

  pendingTasksCount -> (integer)

    

    The number of tasks on the container instance that are in the ``PENDING`` status.

    

    

  agentUpdateStatus -> (string)

    

    The status of the most recent agent update. If an update has never been requested, this value is ``NULL`` .

    

    

  attributes -> (list)

    

    The attributes set for the container instance by the Amazon ECS container agent at instance registration.

    

    (structure)

      

      The attributes applicable to a container instance when it is registered.

      

      name -> (string)

        

        The name of the container instance attribute.

        

        

      value -> (string)

        

        The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

        

        

      

    

  



.. _Manually Updating the Amazon ECS Container Agent: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-agent-update.html#manually_update_agent
.. _amazon-ecs-agent: https://github.com/aws/amazon-ecs-agent/commits/master
