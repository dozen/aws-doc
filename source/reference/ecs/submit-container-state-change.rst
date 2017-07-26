[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs submit-container-state-change:


*****************************
submit-container-state-change
*****************************



===========
Description
===========



.. note::

   

  This action is only used by the Amazon EC2 Container Service agent, and it is not intended for use outside of the agent.

   

 

Sent to acknowledge that a container changed states.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/SubmitContainerStateChange>`_


========
Synopsis
========

::

    submit-container-state-change
  [--cluster <value>]
  [--task <value>]
  [--container-name <value>]
  [--status <value>]
  [--exit-code <value>]
  [--reason <value>]
  [--network-bindings <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that hosts the container.

  

``--task`` (string)


  The task ID or full Amazon Resource Name (ARN) of the task that hosts the container.

  

``--container-name`` (string)


  The name of the container.

  

``--status`` (string)


  The status of the state change request.

  

``--exit-code`` (integer)


  The exit code returned for the state change request.

  

``--reason`` (string)


  The reason for the state change request.

  

``--network-bindings`` (list)


  The network bindings of the container.

  



Shorthand Syntax::

    bindIP=string,containerPort=integer,hostPort=integer,protocol=string ...




JSON Syntax::

  [
    {
      "bindIP": "string",
      "containerPort": integer,
      "hostPort": integer,
      "protocol": "tcp"|"udp"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

acknowledgment -> (string)

  

  Acknowledgement of the state change.

  

  

