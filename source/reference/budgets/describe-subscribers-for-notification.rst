[ :ref:`aws <cli:aws>` . :ref:`budgets <cli:aws budgets>` ]

.. _cli:aws budgets describe-subscribers-for-notification:


*************************************
describe-subscribers-for-notification
*************************************



===========
Description
===========

Get subscribers of a notification

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/budgets-2016-10-20/DescribeSubscribersForNotification>`_


========
Synopsis
========

::

    describe-subscribers-for-notification
  --account-id <value>
  --budget-name <value>
  --notification <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)
Account Id of the customer. It should be a 12 digit number.

``--budget-name`` (string)
A string represents the budget name. No ":" and "\" character is allowed.

``--notification`` (structure)
notification model. Each budget may contain multiple notifications with different settings.



Shorthand Syntax::

    NotificationType=string,ComparisonOperator=string,Threshold=double




JSON Syntax::

  {
    "NotificationType": "ACTUAL"|"FORECASTED",
    "ComparisonOperator": "GREATER_THAN"|"LESS_THAN"|"EQUAL_TO",
    "Threshold": double
  }



``--max-results`` (integer)
An integer to represent how many entries should a pagianted response contains. Maxium is set to 100.

``--next-token`` (string)
A generic String.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Subscribers -> (list)

  A list of subscribers.

  (structure)

    Subscriber model. Each notification may contain multiple subscribers with different addresses.

    SubscriptionType -> (string)

      The subscription type of the subscriber. It can be SMS or EMAIL.

      

    Address -> (string)

      A generic String.

      

    

  

NextToken -> (string)

  A generic String.

  

