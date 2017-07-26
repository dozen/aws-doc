[ :ref:`aws <cli:aws>` . :ref:`stepfunctions <cli:aws stepfunctions>` ]

.. _cli:aws stepfunctions stop-execution:


**************
stop-execution
**************



===========
Description
===========



Stops an execution.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/states-2016-11-23/StopExecution>`_


========
Synopsis
========

::

    stop-execution
  --execution-arn <value>
  [--error <value>]
  [--cause <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--execution-arn`` (string)


  The Amazon Resource Name (ARN) of the execution to stop.

  

``--error`` (string)


  An arbitrary error code that identifies the cause of the termination.

  

``--cause`` (string)


  A more detailed explanation of the cause of the termination.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

stopDate -> (timestamp)

  

  The date the execution was stopped.

  

  

