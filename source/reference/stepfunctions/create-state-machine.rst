[ :ref:`aws <cli:aws>` . :ref:`stepfunctions <cli:aws stepfunctions>` ]

.. _cli:aws stepfunctions create-state-machine:


********************
create-state-machine
********************



===========
Description
===========



Creates a state machine.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/states-2016-11-23/CreateStateMachine>`_


========
Synopsis
========

::

    create-state-machine
  --name <value>
  --definition <value>
  --role-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the state machine. This name must be unique for your AWS account and region.

  

``--definition`` (string)


  The Amazon States Language definition of the state machine.

  

``--role-arn`` (string)


  The Amazon Resource name (ARN) of the IAM role to use for this state machine.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

stateMachineArn -> (string)

  

  The Amazon Resource name (ARN) that identifies the created state machine.

  

  

creationDate -> (timestamp)

  

  The date the state machine was created.

  

  

