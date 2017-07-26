[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-maintenance-window-execution-task-invocations:


******************************************************
describe-maintenance-window-execution-task-invocations
******************************************************



===========
Description
===========



Retrieves the individual task executions (one per target) for a particular task executed as part of a Maintenance Window execution.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeMaintenanceWindowExecutionTaskInvocations>`_


========
Synopsis
========

::

    describe-maintenance-window-execution-task-invocations
  --window-execution-id <value>
  --task-id <value>
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-execution-id`` (string)


  The ID of the Maintenance Window execution the task is part of.

  

``--task-id`` (string)


  The ID of the specific task in the Maintenance Window task that should be retrieved.

  

``--filters`` (list)


  Optional filters used to scope down the returned task invocations. The supported filter key is STATUS with the corresponding values PENDING, IN_PROGRESS, SUCCESS, FAILED, TIMED_OUT, CANCELLING, and CANCELLED.

  



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

**To get the specific task invocations performed for a task execution**

This example lists the invocations for a task executed as part of a maintenance window execution.

Command::

  aws ssm describe-maintenance-window-execution-task-invocations --window-execution-id "518d5565-5969-4cca-8f0e-da3b2a638355" --task-id "ac0c6ae1-daa3-4a89-832e-d384503b6586"

Output::

  {
    "WindowExecutionTaskInvocationIdentities": [
        {
            "Status": "SUCCESS",
            "Parameters": "{\"documentName\":\"AWS-RunShellScript\",\"instanceIds\":[\"i-0000293ffd8c57862\"],\"parameters\":{\"commands\":[\"df\"]},\"maxConcurrency\":\"1\",\"maxErrors\":\"1\"}",
            "InvocationId": "e274b6e1-fe56-4e32-bd2a-8073c6381d8b",
            "StartTime": 1487692834.723,
            "EndTime": 1487692834.871,
            "WindowExecutionId": "518d5565-5969-4cca-8f0e-da3b2a638355",
            "TaskExecutionId": "ac0c6ae1-daa3-4a89-832e-d384503b6586"
        }
    ]
  }


======
Output
======

WindowExecutionTaskInvocationIdentities -> (list)

  

  Information about the task invocation results per invocation.

  

  (structure)

    

    Describes the information about a task invocation for a particular target as part of a task execution performed as part of a Maintenance Window execution.

    

    WindowExecutionId -> (string)

      

      The ID of the Maintenance Window execution that ran the task.

      

      

    TaskExecutionId -> (string)

      

      The ID of the specific task execution in the Maintenance Window execution.

      

      

    InvocationId -> (string)

      

      The ID of the task invocation.

      

      

    ExecutionId -> (string)

      

      The ID of the action performed in the service that actually handled the task invocation. If the task type is RUN_COMMAND, this value is the command ID.

      

      

    Parameters -> (string)

      

      The parameters that were provided for the invocation when it was executed.

      

      

    Status -> (string)

      

      The status of the task invocation.

      

      

    StatusDetails -> (string)

      

      The details explaining the status of the task invocation. Only available for certain Status values. 

      

      

    StartTime -> (timestamp)

      

      The time the invocation started.

      

      

    EndTime -> (timestamp)

      

      The time the invocation finished.

      

      

    OwnerInformation -> (string)

      

      User-provided value that was specified when the target was registered with the Maintenance Window. This was also included in any CloudWatch events raised during the task invocation.

      

      

    WindowTargetId -> (string)

      

      The ID of the target definition in this Maintenance Window the invocation was performed for.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

