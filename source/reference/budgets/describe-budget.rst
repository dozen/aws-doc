[ :ref:`aws <cli:aws>` . :ref:`budgets <cli:aws budgets>` ]

.. _cli:aws budgets describe-budget:


***************
describe-budget
***************



===========
Description
===========

Get a single budget

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/budgets-2016-10-20/DescribeBudget>`_


========
Synopsis
========

::

    describe-budget
  --account-id <value>
  --budget-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)
Account Id of the customer. It should be a 12 digit number.

``--budget-name`` (string)
A string represents the budget name. No ":" and "\" character is allowed.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Budget -> (structure)

  AWS Budget model

  BudgetName -> (string)

    A string represents the budget name. No ":" and "\" character is allowed.

    

  BudgetLimit -> (structure)

    A structure represent either a cost spend or usage spend. Contains an amount and a unit.

    Amount -> (string)

      A string to represent NumericValue.

      

    Unit -> (string)

      A string to represent budget spend unit. It should be not null and not empty.

      

    

  CostFilters -> (map)

    A map represents the cost filters applied to the budget.

    key -> (string)

      A generic String.

      

    value -> (list)

      

      (string)

        A generic String.

        

      

    

  CostTypes -> (structure)

    This includes the options for getting the cost of a budget.

    IncludeTax -> (boolean)

      A generic boolean value.

      

    IncludeSubscription -> (boolean)

      A generic boolean value.

      

    UseBlended -> (boolean)

      A generic boolean value.

      

    

  TimeUnit -> (string)

    The time unit of the budget. e.g. MONTHLY, QUARTERLY, etc.

    

  TimePeriod -> (structure)

    A time period indicated the start date and end date of a budget.

    Start -> (timestamp)

      A generic timestamp. In Java it is transformed to a Date object.

      

    End -> (timestamp)

      A generic timestamp. In Java it is transformed to a Date object.

      

    

  CalculatedSpend -> (structure)

    A structure holds the actual and forecasted spend for a budget.

    ActualSpend -> (structure)

      A structure represent either a cost spend or usage spend. Contains an amount and a unit.

      Amount -> (string)

        A string to represent NumericValue.

        

      Unit -> (string)

        A string to represent budget spend unit. It should be not null and not empty.

        

      

    ForecastedSpend -> (structure)

      A structure represent either a cost spend or usage spend. Contains an amount and a unit.

      Amount -> (string)

        A string to represent NumericValue.

        

      Unit -> (string)

        A string to represent budget spend unit. It should be not null and not empty.

        

      

    

  BudgetType -> (string)

    The type of a budget. It should be COST, USAGE, or RI_UTILIZATION.

    

  

