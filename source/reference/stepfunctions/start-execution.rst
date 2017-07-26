[ :ref:`aws <cli:aws>` . :ref:`stepfunctions <cli:aws stepfunctions>` ]

.. _cli:aws stepfunctions start-execution:


***************
start-execution
***************



===========
Description
===========



Starts a state machine execution.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/states-2016-11-23/StartExecution>`_


========
Synopsis
========

::

    start-execution
  --state-machine-arn <value>
  [--name <value>]
  [--input <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--state-machine-arn`` (string)


  The Amazon Resource name (ARN) of the state machine to execute.

  

``--name`` (string)


  The name of the execution. This name must be unique for your AWS account and region.

  

``--input`` (string)


  The JSON input data for the execution.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

executionArn -> (string)

  

  The Amazon Resource name (ARN) that identifies the execution.

  

  

startDate -> (timestamp)

  

  The date the execution was started.

  

  

