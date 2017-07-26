[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events disable-rule:


************
disable-rule
************



===========
Description
===========



Disables the specified rule. A disabled rule won't match any events, and won't self-trigger if it has a schedule expression.

 

When you disable a rule, incoming events might continue to match to the disabled rule. Please allow a short period of time for changes to take effect.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/DisableRule>`_


========
Synopsis
========

::

    disable-rule
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

**To disable a CloudWatch Events rule**

This example disables the rule named DailyLambdaFunction. The rule is not deleted::

  aws events disable-rule --name "DailyLambdaFunction"


======
Output
======

None