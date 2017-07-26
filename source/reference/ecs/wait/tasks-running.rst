[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` . :ref:`wait <cli:aws ecs wait>` ]

.. _cli:aws ecs wait tasks-running:


*************
tasks-running
*************



===========
Description
===========

Wait until JMESPath query tasks[].lastStatus returns RUNNING for all elements when polling with ``describe-tasks``. It will poll every 6 seconds until a successful state has been reached. This will exit with a return code of 255 after 100 failed checks.

========
Synopsis
========

::

    tasks-running
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



======
Output
======

None