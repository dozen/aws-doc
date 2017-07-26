[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-maintenance-window-execution-tasks:


*******************************************
describe-maintenance-window-execution-tasks
*******************************************



===========
Description
===========



For a given Maintenance Window execution, lists the tasks that were executed.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeMaintenanceWindowExecutionTasks>`_


========
Synopsis
========

::

    describe-maintenance-window-execution-tasks
  --window-execution-id <value>
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-execution-id`` (string)


  The ID of the Maintenance Window execution whose task executions should be retrieved.

  

``--filters`` (list)


  Optional filters used to scope down the returned tasks. The supported filter key is STATUS with the corresponding values PENDING, IN_PROGRESS, SUCCESS, FAILED, TIMED_OUT, CANCELLING, and CANCELLED. 

  



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

**To list all tasks associated with a Maintenance Window Execution**

This example lists the tasks associated with a maintenance window execution.

Command::

  aws ssm describe-maintenance-window-execution-tasks --window-execution-id "518d5565-5969-4cca-8f0e-da3b2a638355"

Output::

  {
    "WindowExecutionTaskIdentities": [
        {
            "Status": "SUCCESS",
            "TaskArn": "AWS-RunShellScript",
            "StartTime": 1487692834.684,
            "TaskType": "RUN_COMMAND",
            "EndTime": 1487692835.005,
            "WindowExecutionId": "518d5565-5969-4cca-8f0e-da3b2a638355",
            "TaskExecutionId": "ac0c6ae1-daa3-4a89-832e-d384503b6586"
        }
    ]
  }


======
Output
======

WindowExecutionTaskIdentities -> (list)

  

  Information about the task executions.

  

  (structure)

    

    Information about a task execution performed as part of a Maintenance Window execution.

    

    WindowExecutionId -> (string)

      

      The ID of the Maintenance Window execution that ran the task.

      

      

    TaskExecutionId -> (string)

      

      The ID of the specific task execution in the Maintenance Window execution.

      

      

    Status -> (string)

      

      The status of the task execution.

      

      

    StatusDetails -> (string)

      

      The details explaining the status of the task execution. Only available for certain status values.

      

      

    StartTime -> (timestamp)

      

      The time the task execution started.

      

      

    EndTime -> (timestamp)

      

      The time the task execution finished.

      

      

    TaskArn -> (string)

      

      The ARN of the executed task.

      

      

    TaskType -> (string)

      

      The type of executed task.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

