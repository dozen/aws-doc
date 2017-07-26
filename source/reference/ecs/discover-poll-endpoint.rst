[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs discover-poll-endpoint:


**********************
discover-poll-endpoint
**********************



===========
Description
===========



.. note::

  

  This action is only used by the Amazon EC2 Container Service agent, and it is not intended for use outside of the agent.

  

 

Returns an endpoint for the Amazon EC2 Container Service agent to poll for updates.



========
Synopsis
========

::

    discover-poll-endpoint
  [--container-instance <value>]
  [--cluster <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--container-instance`` (string)


  The container instance ID or full Amazon Resource Name (ARN) of the container instance. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* .

  

``--cluster`` (string)


  The cluster that the container instance belongs to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

endpoint -> (string)

  

  The endpoint for the Amazon ECS agent to poll.

  

  

telemetryEndpoint -> (string)

  

  The telemetry endpoint for the Amazon ECS agent.

  

  

