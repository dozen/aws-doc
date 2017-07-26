[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events list-rule-names-by-target:


*************************
list-rule-names-by-target
*************************



===========
Description
===========



Lists the names of the rules that the given target is put to. Using this action, you can find out which of the rules in Amazon CloudWatch Events can invoke a specific target in your account. If you have more rules in your account than the given limit, the results will be paginated. In that case, use the next token returned in the response and repeat the ListRulesByTarget action until the next-token in the response is returned as null.



========
Synopsis
========

::

    list-rule-names-by-target
  --target-arn <value>
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--target-arn`` (string)


  The Amazon Resource Name (ARN) of the target resource that you want to list the rules for.

  

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

RuleNames -> (list)

  

  List of rules names that can invoke the given target.

  

  (string)

    

    

  

NextToken -> (string)

  

  Indicates that there are additional results to retrieve.

  

  

