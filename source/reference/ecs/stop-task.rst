[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs stop-task:


*********
stop-task
*********



===========
Description
===========



Stops a running task.

 

When  stop-task is called on a task, the equivalent of ``docker stop`` is issued to the containers running in the task. This results in a ``SIGTERM`` and a default 30-second timeout, after which ``SIGKILL`` is sent and the containers are forcibly stopped. If the container handles the ``SIGTERM`` gracefully and exits within 30 seconds from receiving it, no ``SIGKILL`` is sent.

 

.. note::

   

  The default 30-second timeout can be configured on the Amazon ECS container agent with the ``ECS_CONTAINER_STOP_TIMEOUT`` variable. For more information, see `Amazon ECS Container Agent Configuration <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-agent-config.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/StopTask>`_


========
Synopsis
========

::

    stop-task
  [--cluster <value>]
  --task <value>
  [--reason <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task to stop. If you do not specify a cluster, the default cluster is assumed.

  

``--task`` (string)


  The task ID or full Amazon Resource Name (ARN) entry of the task to stop.

  

``--reason`` (string)


  An optional message specified when a task is stopped. For example, if you are using a custom scheduler, you can use this parameter to specify the reason for stopping the task here, and the message will appear in subsequent  describe-tasks API operations on this task. Up to 255 characters are allowed in this message.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

task -> (structure)

  

  The task that was stopped.

  

  taskArn -> (string)

    

    The Amazon Resource Name (ARN) of the task.

    

    

  clusterArn -> (string)

    

    The Amazon Resource Name (ARN) of the cluster that hosts the task.

    

    

  taskDefinitionArn -> (string)

    

    The Amazon Resource Name (ARN) of the task definition that creates the task.

    

    

  containerInstanceArn -> (string)

    

    The Amazon Resource Name (ARN) of the container instances that host the task.

    

    

  overrides -> (structure)

    

    One or more container overrides.

    

    containerOverrides -> (list)

      

      One or more container overrides sent to a task.

      

      (structure)

        

        The overrides that should be sent to a container.

        

        name -> (string)

          

          The name of the container that receives the override. This parameter is required if any override is specified.

          

          

        command -> (list)

          

          The command to send to the container that overrides the default command from the Docker image or the task definition. You must also specify a container name.

          

          (string)

            

            

          

        environment -> (list)

          

          The environment variables to send to the container. You can add new environment variables, which are added to the container at launch, or you can override the existing environment variables from the Docker image or the task definition. You must also specify a container name.

          

          (structure)

            

            A key and value pair object.

            

            name -> (string)

              

              The name of the key value pair. For environment variables, this is the name of the environment variable.

              

              

            value -> (string)

              

              The value of the key value pair. For environment variables, this is the value of the environment variable.

              

              

            

          

        cpu -> (integer)

          

          The number of ``cpu`` units reserved for the container, instead of the default value from the task definition. You must also specify a container name.

          

          

        memory -> (integer)

          

          The hard limit (in MiB) of memory to present to the container, instead of the default value from the task definition. If your container attempts to exceed the memory specified here, the container is killed. You must also specify a container name.

          

          

        memoryReservation -> (integer)

          

          The soft limit (in MiB) of memory to reserve for the container, instead of the default value from the task definition. You must also specify a container name.

          

          

        

      

    taskRoleArn -> (string)

      

      The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

      

      

    

  lastStatus -> (string)

    

    The last known status of the task.

    

    

  desiredStatus -> (string)

    

    The desired status of the task.

    

    

  containers -> (list)

    

    The containers associated with the task.

    

    (structure)

      

      A Docker container that is part of a task.

      

      containerArn -> (string)

        

        The Amazon Resource Name (ARN) of the container.

        

        

      taskArn -> (string)

        

        The Amazon Resource Name (ARN) of the task.

        

        

      name -> (string)

        

        The name of the container.

        

        

      lastStatus -> (string)

        

        The last known status of the container.

        

        

      exitCode -> (integer)

        

        The exit code returned from the container.

        

        

      reason -> (string)

        

        A short (255 max characters) human-readable string to provide additional details about a running or stopped container.

        

        

      networkBindings -> (list)

        

        The network bindings associated with the container.

        

        (structure)

          

          Details on the network bindings between a container and its host container instance. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  describe-tasks API responses.

          

          bindIP -> (string)

            

            The IP address that the container is bound to on the container instance.

            

            

          containerPort -> (integer)

            

            The port number on the container that is be used with the network binding.

            

            

          hostPort -> (integer)

            

            The port number on the host that is used with the network binding.

            

            

          protocol -> (string)

            

            The protocol used for the network binding.

            

            

          

        

      

    

  startedBy -> (string)

    

    The tag specified when a task is started. If the task is started by an Amazon ECS service, then the ``startedBy`` parameter contains the deployment ID of the service that starts it.

    

    

  version -> (long)

    

    The version counter for the task. Every time a task experiences a change that triggers a CloudWatch event, the version counter is incremented. If you are replicating your Amazon ECS task state with CloudWatch events, you can compare the version of a task reported by the Amazon ECS APIs with the version reported in CloudWatch events for the task (inside the ``detail`` object) to verify that the version in your event stream is current.

    

    

  stoppedReason -> (string)

    

    The reason the task was stopped.

    

    

  createdAt -> (timestamp)

    

    The Unix timestamp for when the task was created (the task entered the ``PENDING`` state).

    

    

  startedAt -> (timestamp)

    

    The Unix timestamp for when the task was started (the task transitioned from the ``PENDING`` state to the ``RUNNING`` state).

    

    

  stoppedAt -> (timestamp)

    

    The Unix timestamp for when the task was stopped (the task transitioned from the ``RUNNING`` state to the ``STOPPED`` state).

    

    

  group -> (string)

    

    The name of the task group associated with the task.

    

    

  

