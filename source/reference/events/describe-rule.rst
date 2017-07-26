[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events describe-rule:


*************
describe-rule
*************



===========
Description
===========



Describes the details of the specified rule.



========
Synopsis
========

::

    describe-rule
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the rule you want to describe details for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Name -> (string)

  

  The rule's name.

  

  

Arn -> (string)

  

  The Amazon Resource Name (ARN) associated with the rule.

  

  

EventPattern -> (string)

  

  The event pattern.

  

  

ScheduleExpression -> (string)

  

  The scheduling expression. For example, "cron(0 20 * * ? *)", "rate(5 minutes)".

  

  

State -> (string)

  

  Specifies whether the rule is enabled or disabled.

  

  

Description -> (string)

  

  The rule's description.

  

  

RoleArn -> (string)

  

  The Amazon Resource Name (ARN) of the IAM role associated with the rule.

  

  

