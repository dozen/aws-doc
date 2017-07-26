[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` . :ref:`wait <cli:aws ec2 wait>` ]

.. _cli:aws ec2 wait export-task-completed:


*********************
export-task-completed
*********************



===========
Description
===========

Wait until JMESPath query ExportTasks[].State returns completed for all elements when polling with ``describe-export-tasks``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeExportTasks>`_


========
Synopsis
========

::

    export-task-completed
  [--export-task-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--export-task-ids`` (list)


  One or more export task IDs.

  



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