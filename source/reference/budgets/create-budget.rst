[ :ref:`aws <cli:aws>` . :ref:`budgets <cli:aws budgets>` ]

.. _cli:aws budgets create-budget:


*************
create-budget
*************



===========
Description
===========

Create a new budget

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/budgets-2016-10-20/CreateBudget>`_


========
Synopsis
========

::

    create-budget
  --account-id <value>
  --budget <value>
  [--notifications-with-subscribers <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)
Account Id of the customer. It should be a 12 digit number.

``--budget`` (structure)
AWS budget model



Shorthand Syntax::

    BudgetName=string,BudgetLimit={Amount=string,Unit=string},CostFilters={KeyName1=string,string,KeyName2=string,string},CostTypes={IncludeTax=boolean,IncludeSubscription=boolean,UseBlended=boolean},TimeUnit=string,TimePeriod={Start=timestamp,End=timestamp},CalculatedSpend={ActualSpend={Amount=string,Unit=string},ForecastedSpend={Amount=string,Unit=string}},BudgetType=string




JSON Syntax::

  {
    "BudgetName": "string",
    "BudgetLimit": {
      "Amount": "string",
      "Unit": "string"
    },
    "CostFilters": {"string": ["string", ...]
      ...},
    "CostTypes": {
      "IncludeTax": true|false,
      "IncludeSubscription": true|false,
      "UseBlended": true|false
    },
    "TimeUnit": "DAILY"|"MONTHLY"|"QUARTERLY"|"ANNUALLY",
    "TimePeriod": {
      "Start": timestamp,
      "End": timestamp
    },
    "CalculatedSpend": {
      "ActualSpend": {
        "Amount": "string",
        "Unit": "string"
      },
      "ForecastedSpend": {
        "Amount": "string",
        "Unit": "string"
      }
    },
    "BudgetType": "USAGE"|"COST"|"RI_UTILIZATION"
  }



``--notifications-with-subscribers`` (list)
A list of Notifications, each with a list of subscribers.



Shorthand Syntax::

    Notification={NotificationType=string,ComparisonOperator=string,Threshold=double},Subscribers=[{SubscriptionType=string,Address=string},{SubscriptionType=string,Address=string}] ...




JSON Syntax::

  [
    {
      "Notification": {
        "NotificationType": "ACTUAL"|"FORECASTED",
        "ComparisonOperator": "GREATER_THAN"|"LESS_THAN"|"EQUAL_TO",
        "Threshold": double
      },
      "Subscribers": [
        {
          "SubscriptionType": "SNS"|"EMAIL",
          "Address": "string"
        }
        ...
      ]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

