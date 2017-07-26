[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` . :ref:`wait <cli:aws ecs wait>` ]

.. _cli:aws ecs wait tasks-stopped:


*************
tasks-stopped
*************



===========
Description
===========

Wait until JMESPath query tasks[].lastStatus returns STOPPED for all elements when polling with ``describe-tasks``. It will poll every 6 seconds until a successful state has been reached. This will exit with a return code of 255 after 100 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/DescribeTasks>`_


========
Synopsis
========

::

    tasks-stopped
  [--cluster <value>]
  --tasks <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that hosts the task to describe. If you do not specify a cluster, the default cluster is assumed.

  

``--tasks`` (list)


  A list of up to 100 task IDs or full Amazon Resource Name (ARN) entries.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None