[ :ref:`aws <cli:aws>` . :ref:`stepfunctions <cli:aws stepfunctions>` ]

.. _cli:aws stepfunctions describe-state-machine:


**********************
describe-state-machine
**********************



===========
Description
===========



Describes a state machine.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/states-2016-11-23/DescribeStateMachine>`_


========
Synopsis
========

::

    describe-state-machine
  --state-machine-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--state-machine-arn`` (string)


  The Amazon Resource Name (ARN) of the state machine to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

stateMachineArn -> (string)

  

  The Amazon Resource Name (ARN) that identifies the state machine.

  

  

name -> (string)

  

  The name of the state machine.

  

  

status -> (string)

  

  The current status of the state machine.

  

  

definition -> (string)

  

  The Amazon States Language definition of the state machine.

  

  

roleArn -> (string)

  

  The Amazon Resource Name (ARN) of the IAM role used for executing this state machine.

  

  

creationDate -> (timestamp)

  

  The date the state machine was created.

  

  

