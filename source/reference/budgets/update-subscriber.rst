[ :ref:`aws <cli:aws>` . :ref:`budgets <cli:aws budgets>` ]

.. _cli:aws budgets update-subscriber:


*****************
update-subscriber
*****************



===========
Description
===========

Update a subscriber

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/budgets-2016-10-20/UpdateSubscriber>`_


========
Synopsis
========

::

    update-subscriber
  --account-id <value>
  --budget-name <value>
  --notification <value>
  --old-subscriber <value>
  --new-subscriber <value>
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



``--old-subscriber`` (structure)
old-subscriber model. Each notification may contain multiple subscribers with different addresses.



Shorthand Syntax::

    SubscriptionType=string,Address=string




JSON Syntax::

  {
    "SubscriptionType": "SNS"|"EMAIL",
    "Address": "string"
  }



``--new-subscriber`` (structure)
old-subscriber model. Each notification may contain multiple subscribers with different addresses.



Shorthand Syntax::

    SubscriptionType=string,Address=string




JSON Syntax::

  {
    "SubscriptionType": "SNS"|"EMAIL",
    "Address": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

