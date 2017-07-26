[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events list-rules:


**********
list-rules
**********



===========
Description
===========



Lists your Amazon CloudWatch Events rules. You can either list all the rules or you can provide a prefix to match to the rule names.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/ListRules>`_


========
Synopsis
========

::

    list-rules
  [--name-prefix <value>]
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name-prefix`` (string)


  The prefix matching the rule name.

  

``--next-token`` (string)


  The token returned by a previous call to retrieve the next set of results.

  

``--limit`` (integer)


  The maximum number of results to return.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To display a list of all CloudWatch Events rules**

This example displays all CloudWatch Events rules in the region::

  aws events list-rules

**To display a list of CloudWatch Events rules beginning with a certain string.**

This example displays all CloudWatch Events rules in the region that have a name starting with "Daily"::

  aws events list-rules --name-prefix "Daily"


======
Output
======

Rules -> (list)

  

  The rules that match the specified criteria.

  

  (structure)

    

    Contains information about a rule in Amazon CloudWatch Events.

    

    Name -> (string)

      

      The name of the rule.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) of the rule.

      

      

    EventPattern -> (string)

      

      The event pattern of the rule. For more information, see `Events and Event Patterns <http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/CloudWatchEventsandEventPatterns.html>`_ in the *Amazon CloudWatch Events User Guide* .

      

      

    State -> (string)

      

      The state of the rule.

      

      

    Description -> (string)

      

      The description of the rule.

      

      

    ScheduleExpression -> (string)

      

      The scheduling expression. For example, "cron(0 20 * * ? *)", "rate(5 minutes)".

      

      

    RoleArn -> (string)

      

      The Amazon Resource Name (ARN) of the role that is used for target invocation.

      

      

    

  

NextToken -> (string)

  

  Indicates whether there are additional results to retrieve. If there are no more results, the value is null.

  

  

