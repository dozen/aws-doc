[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs submit-task-state-change:


************************
submit-task-state-change
************************



===========
Description
===========



.. note::

  

  This action is only used by the Amazon EC2 Container Service agent, and it is not intended for use outside of the agent.

  

 

Sent to acknowledge that a task changed states.



========
Synopsis
========

::

    submit-task-state-change
  [--cluster <value>]
  [--task <value>]
  [--status <value>]
  [--reason <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task.

  

``--task`` (string)


  The task ID or full Amazon Resource Name (ARN) of the task in the state change request.

  

``--status`` (string)


  The status of the state change request.

  

``--reason`` (string)


  The reason for the state change request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

acknowledgment -> (string)

  

  Acknowledgement of the state change.

  

  

