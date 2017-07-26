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
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

acknowledgment -> (string)

  

  Acknowledgement of the state change.

  

  

