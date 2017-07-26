[ :ref:`aws <cli:aws>` . :ref:`stepfunctions <cli:aws stepfunctions>` ]

.. _cli:aws stepfunctions describe-execution:


******************
describe-execution
******************



===========
Description
===========



Describes an execution.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/states-2016-11-23/DescribeExecution>`_


========
Synopsis
========

::

    describe-execution
  --execution-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--execution-arn`` (string)


  The Amazon Resource Name (ARN) of the execution to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

executionArn -> (string)

  

  The Amazon Resource Name (ARN) that identifies the execution.

  

  

stateMachineArn -> (string)

  

  The Amazon Resource Name (ARN) of the executed stated machine.

  

  

name -> (string)

  

  The name of the execution.

  

  

status -> (string)

  

  The current status of the execution.

  

  

startDate -> (timestamp)

  

  The date the execution was started.

  

  

stopDate -> (timestamp)

  

  If the execution has already ended, the date the execution stopped.

  

  

input -> (string)

  

  The JSON input data of the execution.

  

  

output -> (string)

  

  The JSON output data of the execution.

  

  

