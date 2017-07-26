[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-maintenance-window-executions:


**************************************
describe-maintenance-window-executions
**************************************



===========
Description
===========



Lists the executions of a Maintenance Window (meaning, information about when the Maintenance Window was scheduled to be active and information about tasks registered and run with the Maintenance Window).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeMaintenanceWindowExecutions>`_


========
Synopsis
========

::

    describe-maintenance-window-executions
  --window-id <value>
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-id`` (string)


  The ID of the Maintenance Window whose executions should be retrieved.

  

``--filters`` (list)


  Each entry in the array is a structure containing:

   

  Key (string, between 1 and 128 characters)

   

  Values (array of strings, each string is between 1 and 256 characters)

   

  The supported Keys are ExecutedBefore and ExecutedAfter with the value being a date/time string such as 2016-11-04T05:00:00Z.

  



Shorthand Syntax::

    Key=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--max-results`` (integer)


  The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list all executions for a Maintenance Window**

This example lists all of the executions for a maintenance window.

Command::

  aws ssm describe-maintenance-window-executions --window-id "mw-ab12cd34ef56gh78"

Output::

  {
    "WindowExecutions": [
        {
            "Status": "SUCCESS",
            "WindowId": "mw-06cf17cbefcb4bf4f",
            "StartTime": 1487692834.595,
            "EndTime": 1487692835.051,
            "WindowExecutionId": "518d5565-5969-4cca-8f0e-da3b2a638355"
        }
    ]
  }

**To list all executions for a maintenance window before a specified date**

This example lists all of the executions for a maintenance window before a specific date.

Command::

  aws ssm describe-maintenance-window-executions --window-id "mw-ab12cd34ef56gh78" --filters "Key=ExecutedBefore,Values=2016-11-04T05:00:00Z"
  
**To list all executions for a maintenance window after a specified date**

This example lists all of the executions for maintenance window after a specific date.

Command::

  aws ssm describe-maintenance-window-executions --window-id "mw-ab12cd34ef56gh78" --filters "Key=ExecutedAfter,Values=2016-11-04T17:00:00Z"

======
Output
======

WindowExecutions -> (list)

  

  Information about the Maintenance Windows execution.

  

  (structure)

    

    Describes the information about an execution of a Maintenance Window. 

    

    WindowId -> (string)

      

      The ID of the Maintenance Window.

      

      

    WindowExecutionId -> (string)

      

      The ID of the Maintenance Window execution.

      

      

    Status -> (string)

      

      The status of the execution.

      

      

    StatusDetails -> (string)

      

      The details explaining the Status. Only available for certain status values.

      

      

    StartTime -> (timestamp)

      

      The time the execution started.

      

      

    EndTime -> (timestamp)

      

      The time the execution finished.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

