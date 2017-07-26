[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events list-rules:


**********
list-rules
**********



===========
Description
===========



Lists the Amazon CloudWatch Events rules in your account. You can either list all the rules or you can provide a prefix to match to the rule names. If you have more rules in your account than the given limit, the results will be paginated. In that case, use the next token returned in the response and repeat the list-rules action until the next-token in the response is returned as null.



========
Synopsis
========

::

    list-rules
  [--name-prefix <value>]
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name-prefix`` (string)


  The prefix matching the rule name.

  

``--next-token`` (string)


  The token returned by a previous call to indicate that there is more data available.

  

``--limit`` (integer)


  The maximum number of results to return.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Rules -> (list)

  

  List of rules matching the specified criteria.

  

  (structure)

    

    Contains information about a rule in Amazon CloudWatch Events. A ListRulesResult contains a list of Rules.

    

    Name -> (string)

      

      The rule's name.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) of the rule.

      

      

    EventPattern -> (string)

      

      The event pattern of the rule.

      

      

    State -> (string)

      

      The rule's state.

      

      

    Description -> (string)

      

      The description of the rule.

      

      

    ScheduleExpression -> (string)

      

      The scheduling expression. For example, "cron(0 20 * * ? *)", "rate(5 minutes)".

      

      

    RoleArn -> (string)

      

      The Amazon Resource Name (ARN) associated with the role that is used for target invocation.

      

      

    

  

NextToken -> (string)

  

  Indicates that there are additional results to retrieve.

  

  

