[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs describe-tasks:


**************
describe-tasks
**************



===========
Description
===========



Describes a specified task or tasks.



========
Synopsis
========

::

    describe-tasks
  [--cluster <value>]
  --tasks <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task to describe. If you do not specify a cluster, the default cluster is assumed.

  

``--tasks`` (list)


  A space-separated list of task IDs or full Amazon Resource Name (ARN) entries.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe a task**

This example command provides a description of the specified task, using the task UUID as an identifier.

Command::

  aws ecs describe-tasks --tasks c5cba4eb-5dad-405e-96db-71ef8eefe6a8

Output::

	{
	    "failures": [],
	    "tasks": [
	        {
	            "taskArn": "arn:aws:ecs:<region>:<aws_account_id>:task/c5cba4eb-5dad-405e-96db-71ef8eefe6a8",
	            "overrides": {
	                "containerOverrides": [
	                    {
	                        "name": "ecs-demo"
	                    }
	                ]
	            },
	            "lastStatus": "RUNNING",
	            "containerInstanceArn": "arn:aws:ecs:<region>:<aws_account_id>:container-instance/18f9eda5-27d7-4c19-b133-45adc516e8fb",
	            "clusterArn": "arn:aws:ecs:<region>:<aws_account_id>:cluster/default",
	            "desiredStatus": "RUNNING",
	            "taskDefinitionArn": "arn:aws:ecs:<region>:<aws_account_id>:task-definition/amazon-ecs-sample:1",
	            "startedBy": "ecs-svc/9223370608528463088",
	            "containers": [
	                {
	                    "containerArn": "arn:aws:ecs:<region>:<aws_account_id>:container/7c01765b-c588-45b3-8290-4ba38bd6c5a6",
	                    "taskArn": "arn:aws:ecs:<region>:<aws_account_id>:task/c5cba4eb-5dad-405e-96db-71ef8eefe6a8",
	                    "lastStatus": "RUNNING",
	                    "name": "ecs-demo",
	                    "networkBindings": [
	                        {
	                            "bindIP": "0.0.0.0",
	                            "containerPort": 80,
	                            "hostPort": 80
	                        }
	                    ]
	                }
	            ]
	        }
	    ]
	}


======
Output
======

tasks -> (list)

  

  The list of tasks.

  

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

      

      

    

  

