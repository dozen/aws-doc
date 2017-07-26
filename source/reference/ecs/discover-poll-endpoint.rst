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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/DiscoverPollEndpoint>`_


========
Synopsis
========

::

    discover-poll-endpoint
  [--container-instance <value>]
  [--cluster <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--container-instance`` (string)


  The container instance ID or full Amazon Resource Name (ARN) of the container instance. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, ``arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* `` .

  

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that the container instance belongs to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

endpoint -> (string)

  

  The endpoint for the Amazon ECS agent to poll.

  

  

telemetryEndpoint -> (string)

  

  The telemetry endpoint for the Amazon ECS agent.

  

  

