[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs run-task:


********
run-task
********



===========
Description
===========



Start a task using random placement and the default Amazon ECS scheduler. To use your own scheduler or place a task on a specific container instance, use ``start-task`` instead.

 

.. warning::

   

  The ``count`` parameter is limited to 10 tasks per call.

   



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
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster on which to run your task. If you do not specify a cluster, the default cluster is assumed..

  

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
        ]
      }
      ...
    ]
  }



``--count`` (integer)


  The number of instantiations of the specified task to place on your cluster.

   

  .. warning::

     

    The ``count`` parameter is limited to 10 tasks per call.

     

  

``--started-by`` (string)


  An optional tag specified when a task is started. For example if you automatically trigger a task to run a batch process job, you could apply a unique identifier for that job to your task with the ``startedBy`` parameter. You can then identify which tasks belong to that job by filtering the results of a  list-tasks call with the ``startedBy`` value.

   

  If a task is started by an Amazon ECS service, then the ``startedBy`` parameter contains the deployment ID of the service that starts it.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      The Amazon Resource Name (ARN) of the of the cluster that hosts the task.

      

      

    taskDefinitionArn -> (string)

      

      The Amazon Resource Name (ARN) of the of the task definition that creates the task.

      

      

    containerInstanceArn -> (string)

      

      The Amazon Resource Name (ARN) of the container instances that host the task.

      

      

    overrides -> (structure)

      

      One or more container overrides.

      

      containerOverrides -> (list)

        

        One or more container overrides sent to a task.

        

        (structure)

          

          The overrides that should be sent to a container.

          

          name -> (string)

            

            The name of the container that receives the override.

            

            

          command -> (list)

            

            The command to send to the container that overrides the default command from the Docker image or the task definition.

            

            (string)

              

              

            

          environment -> (list)

            

            The environment variables to send to the container. You can add new environment variables, which are added to the container at launch, or you can override the existing environment variables from the Docker image or the task definition.

            

            (structure)

              

              A key and value pair object.

              

              name -> (string)

                

                The name of the key value pair. For environment variables, this is the name of the environment variable.

                

                

              value -> (string)

                

                The value of the key value pair. For environment variables, this is the value of the environment variable.

                

                

              

            

          

        

      

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

          

          A short (255 max characters) human-readable string to provide additional detail about a running or stopped container.

          

          

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

      

      

    stoppedReason -> (string)

      

      The reason the task was stopped.

      

      

    createdAt -> (timestamp)

      

      The Unix time in seconds and milliseconds when the task was created (the task entered the ``PENDING`` state).

      

      

    startedAt -> (timestamp)

      

      The Unix time in seconds and milliseconds when the task was started (the task transitioned from the ``PENDING`` state to the ``RUNNING`` state).

      

      

    stoppedAt -> (timestamp)

      

      The Unix time in seconds and milliseconds when the task was stopped (the task transitioned from the ``RUNNING`` state to the ``STOPPED`` state).

      

      

    

  

failures -> (list)

  

  Any failures associated with the call.

  

  (structure)

    

    A failed resource.

    

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the failed resource.

      

      

    reason -> (string)

      

      The reason for the failure.

      

      

    

  

