[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs run-task:


********
run-task
********



===========
Description
===========



Starts a new task using the specified task definition.

 

You can allow Amazon ECS to place tasks for you, or you can customize how Amazon ECS places tasks using placement constraints and placement strategies. For more information, see `Scheduling Tasks <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

 

Alternatively, you can use  start-task to use your own scheduler or place tasks manually on specific container instances.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/RunTask>`_


========
Synopsis
========

::

    run-task
  [--cluster <value>]
  --task-definition <value>
  [--overrides <value>]
  [--count <value>]
  [--started-by <value>]
  [--group <value>]
  [--placement-constraints <value>]
  [--placement-strategy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster on which to run your task. If you do not specify a cluster, the default cluster is assumed.

  

``--task-definition`` (string)


  The ``family`` and ``revision`` (``family:revision`` ) or full Amazon Resource Name (ARN) of the task definition to run. If a ``revision`` is not specified, the latest ``ACTIVE`` revision is used.

  

``--overrides`` (structure)


  A list of container overrides in JSON format that specify the name of a container in the specified task definition and the overrides it should receive. You can override the default command for a container (that is specified in the task definition or Docker image) with a ``command`` override. You can also override existing environment variables (that are specified in the task definition or Docker image) on a container or add new environment variables to it with an ``environment`` override.

   

  .. note::

     

    A total of 8192 characters are allowed for overrides. This limit includes the JSON formatting characters of the override structure.

     

  



JSON Syntax::

  {
    "containerOverrides": [
      {
        "name": "string",
        "command": ["string", ...],
        "environment": [
          {
            "name": "string",
            "value": "string"
          }
          ...
        ],
        "cpu": integer,
        "memory": integer,
        "memoryReservation": integer
      }
      ...
    ],
    "taskRoleArn": "string"
  }



``--count`` (integer)


  The number of instantiations of the specified task to place on your cluster. You can specify up to 10 tasks per call.

  

``--started-by`` (string)


  An optional tag specified when a task is started. For example if you automatically trigger a task to run a batch process job, you could apply a unique identifier for that job to your task with the ``startedBy`` parameter. You can then identify which tasks belong to that job by filtering the results of a  list-tasks call with the ``startedBy`` value. Up to 36 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed.

   

  If a task is started by an Amazon ECS service, then the ``startedBy`` parameter contains the deployment ID of the service that starts it.

  

``--group`` (string)


  The name of the task group to associate with the task. The default value is the family name of the task definition (for example, family:my-family-name).

  

``--placement-constraints`` (list)


  An array of placement constraint objects to use for the task. You can specify up to 10 constraints per task (including constraints in the task definition and those specified at run time).

  



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


  The placement strategy objects to use for the task. You can specify a maximum of 5 strategy rules per task.

  



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

**To run a task on your default cluster**

This example command runs the specified task definition on your default cluster.

Command::

  aws ecs run-task --cluster default --task-definition sleep360:1

Output::

	{
	    "tasks": [
	        {
	            "taskArn": "arn:aws:ecs:us-east-1:<aws_account_id>:task/a9f21ea7-c9f5-44b1-b8e6-b31f50ed33c0",
	            "overrides": {
	                "containerOverrides": [
	                    {
	                        "name": "sleep"
	                    }
	                ]
	            },
	            "lastStatus": "PENDING",
	            "containerInstanceArn": "arn:aws:ecs:us-east-1:<aws_account_id>:container-instance/ffe3d344-77e2-476c-a4d0-bf560ad50acb",
	            "desiredStatus": "RUNNING",
	            "taskDefinitionArn": "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/sleep360:1",
	            "containers": [
	                {
	                    "containerArn": "arn:aws:ecs:us-east-1:<aws_account_id>:container/58591c8e-be29-4ddf-95aa-ee459d4c59fd",
	                    "taskArn": "arn:aws:ecs:us-east-1:<aws_account_id>:task/a9f21ea7-c9f5-44b1-b8e6-b31f50ed33c0",
	                    "lastStatus": "PENDING",
	                    "name": "sleep"
	                }
	            ]
	        }
	    ]
	}


======
Output
======

tasks -> (list)

  

  A full description of the tasks that were run. Each task that was successfully placed on your cluster are described here.

  

  (structure)

    

    Details on a task in a cluster.

    

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

      

      

    

  

failures -> (list)

  

  Any failures associated with the call.

  

  (structure)

    

    A failed resource.

    

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the failed resource.

      

      

    reason -> (string)

      

      The reason for the failure.

      

      

    

  

