[ :ref:`aws <cli:aws>` . :ref:`budgets <cli:aws budgets>` ]

.. _cli:aws budgets update-budget:


*************
update-budget
*************



===========
Description
===========

Update the information of a budget already created

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/budgets-2016-10-20/UpdateBudget>`_


========
Synopsis
========

::

    update-budget
  --account-id <value>
  --new-budget <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)
Account Id of the customer. It should be a 12 digit number.

``--new-budget`` (structure)
AWS new-budget model



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

