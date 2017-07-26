[ :ref:`aws <cli:aws>` . :ref:`budgets <cli:aws budgets>` ]

.. _cli:aws budgets describe-notifications-for-budget:


*********************************
describe-notifications-for-budget
*********************************



===========
Description
===========

Get notifications of a budget

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/budgets-2016-10-20/DescribeNotificationsForBudget>`_


========
Synopsis
========

::

    describe-notifications-for-budget
  --account-id <value>
  --budget-name <value>
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

Notifications -> (list)

  A list of notifications.

  (structure)

    Notification model. Each budget may contain multiple notifications with different settings.

    NotificationType -> (string)

      The type of a notification. It should be ACTUAL or FORECASTED.

      

    ComparisonOperator -> (string)

      The comparison operator of a notification. Currently we support less than, equal to and greater than.

      

    Threshold -> (double)

      The threshold of the a notification. It should be a number between 0 and 100.

      

    

  

NextToken -> (string)

  A generic String.

  

