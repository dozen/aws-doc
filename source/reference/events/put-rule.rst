[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events put-rule:


********
put-rule
********



===========
Description
===========



Creates or updates a rule. Rules are enabled by default, or based on value of the State parameter. You can disable a rule using  disable-rule .

 

 **Note:** When you make a change with this action, incoming events might not immediately start matching to new or updated rules. Please allow a short period of time for changes to take effect.

 

A rule must contain at least an event-pattern or ScheduleExpression. Rules with EventPatterns are triggered when a matching event is observed. Rules with ScheduleExpressions self-trigger based on the given schedule. A rule can have both an event-pattern and a ScheduleExpression, in which case the rule will trigger on matching events as well as on a schedule.

 

 **Note:** Most services in AWS treat : or / as the same character in Amazon Resource Names (ARNs). However, CloudWatch Events uses an exact match in event patterns and rules. Be sure to use the correct ARN characters when creating event patterns so that they match the ARN syntax in the event you want to match. 



========
Synopsis
========

::

    put-rule
  --name <value>
  [--schedule-expression <value>]
  [--event-pattern <value>]
  [--state <value>]
  [--description <value>]
  [--role-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the rule that you are creating or updating.

  

``--schedule-expression`` (string)


  The scheduling expression. For example, "cron(0 20 * * ? *)", "rate(5 minutes)".

  

``--event-pattern`` (string)


  The event pattern.

  

``--state`` (string)


  Indicates whether the rule is enabled or disabled.

  

  Possible values:

  
  *   ``ENABLED``

  
  *   ``DISABLED``

  

  

``--description`` (string)


  A description of the rule.

  

``--role-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM role associated with the rule.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

RuleArn -> (string)

  

  The Amazon Resource Name (ARN) that identifies the rule.

  

  

