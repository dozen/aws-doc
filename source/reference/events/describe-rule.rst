[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events describe-rule:


*************
describe-rule
*************



===========
Description
===========



Describes the specified rule.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/DescribeRule>`_


========
Synopsis
========

::

    describe-rule
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the rule.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To display information about a CloudWatch Events rule**

This example displays information about the rule named DailyLambdaFunction::

  aws events describe-rule --name "DailyLambdaFunction"


======
Output
======

Name -> (string)

  

  The name of the rule.

  

  

Arn -> (string)

  

  The Amazon Resource Name (ARN) of the rule.

  

  

EventPattern -> (string)

  

  The event pattern. For more information, see `Events and Event Patterns <http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/CloudWatchEventsandEventPatterns.html>`_ in the *Amazon CloudWatch Events User Guide* .

  

  

ScheduleExpression -> (string)

  

  The scheduling expression. For example, "cron(0 20 * * ? *)", "rate(5 minutes)".

  

  

State -> (string)

  

  Specifies whether the rule is enabled or disabled.

  

  

Description -> (string)

  

  The description of the rule.

  

  

RoleArn -> (string)

  

  The Amazon Resource Name (ARN) of the IAM role associated with the rule.

  

  

