[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events list-rule-names-by-target:


*************************
list-rule-names-by-target
*************************



===========
Description
===========



Lists the rules for the specified target. You can see which of the rules in Amazon CloudWatch Events can invoke a specific target in your account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/ListRuleNamesByTarget>`_


========
Synopsis
========

::

    list-rule-names-by-target
  --target-arn <value>
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--target-arn`` (string)


  The Amazon Resource Name (ARN) of the target resource.

  

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

**To display all the rules that have a specified target**

This example displays all rules that have the Lambda function named "MyFunctionName" as the target::

  aws events list-rule-names-by-target --target-arn "arn:aws:lambda:us-east-1:123456789012:function:MyFunctionName"


======
Output
======

RuleNames -> (list)

  

  The names of the rules that can invoke the given target.

  

  (string)

    

    

  

NextToken -> (string)

  

  Indicates whether there are additional results to retrieve. If there are no more results, the value is null.

  

  

