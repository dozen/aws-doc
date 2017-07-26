[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events put-rule:


********
put-rule
********



===========
Description
===========



Creates or updates the specified rule. Rules are enabled by default, or based on value of the state. You can disable a rule using  disable-rule .

 

When you create or update a rule, incoming events might not immediately start matching to new or updated rules. Please allow a short period of time for changes to take effect.

 

A rule must contain at least an event-pattern or ScheduleExpression. Rules with EventPatterns are triggered when a matching event is observed. Rules with ScheduleExpressions self-trigger based on the given schedule. A rule can have both an event-pattern and a ScheduleExpression, in which case the rule triggers on matching events as well as on a schedule.

 

Most services in AWS treat : or / as the same character in Amazon Resource Names (ARNs). However, CloudWatch Events uses an exact match in event patterns and rules. Be sure to use the correct ARN characters when creating event patterns so that they match the ARN syntax in the event you want to match.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/PutRule>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the rule that you are creating or updating.

  

``--schedule-expression`` (string)


  The scheduling expression. For example, "cron(0 20 * * ? *)" or "rate(5 minutes)".

  

``--event-pattern`` (string)


  The event pattern. For more information, see `Events and Event Patterns <http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/CloudWatchEventsandEventPatterns.html>`_ in the *Amazon CloudWatch Events User Guide* .

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create CloudWatch Events rules**

This example creates a rule that triggers every day at 9:00am (UTC).  If you use put-targets to add a Lambda function as a target of this rule, you could run the Lambda function every day at the specified time::

  aws events put-rule --name "DailyLambdaFunction" --schedule-expression "cron(0 9 * * ? *)"     

This example creates a rule that triggers when any EC2 instance in the region changes state::

  aws events put-rule --name "EC2InstanceStateChanges" --event-pattern "{\"source\":[\"aws.ec2\"],\"detail-type\":[\"EC2 Instance State-change Notification\"]}"  --role-arn "arn:aws:iam::123456789012:role/MyRoleForThisRule"

This example creates a rule that triggers when any EC2 instance in the region is stopped or terminated::

  aws events put-rule --name "EC2InstanceStateChangeStopOrTerminate" --event-pattern "{\"source\":[\"aws.ec2\"],\"detail-type\":[\"EC2 Instance State-change Notification\"],\"detail\":{\"state\":[\"stopped\",\"terminated\"]}}" --role-arn "arn:aws:iam::123456789012:role/MyRoleForThisRule" 


======
Output
======

RuleArn -> (string)

  

  The Amazon Resource Name (ARN) of the rule.

  

  

