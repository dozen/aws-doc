[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-maintenance-window-execution-task:


*************************************
get-maintenance-window-execution-task
*************************************



===========
Description
===========



Retrieves the details about a specific task executed as part of a Maintenance Window execution.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetMaintenanceWindowExecutionTask>`_


========
Synopsis
========

::

    get-maintenance-window-execution-task
  --window-execution-id <value>
  --task-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-execution-id`` (string)


  The ID of the Maintenance Window execution that includes the task.

  

``--task-id`` (string)


  The ID of the specific task execution in the Maintenance Window task that should be retrieved.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about a Maintenance Window task execution**

This example lists information about a task that was part of a maintenance window execution.

Command::

  aws ssm get-maintenance-window-execution-task --window-execution-id "518d5565-5969-4cca-8f0e-da3b2a638355" --task-id "ac0c6ae1-daa3-4a89-832e-d384503b6586"

Output::

  {
    "Status": "SUCCESS",
    "MaxErrors": "1",
    "TaskArn": "AWS-RunShellScript",
    "MaxConcurrency": "1",
    "ServiceRole": "arn:aws:iam::812345678901:role/MaintenanceWindowsRole",
    "WindowExecutionId": "518d5565-5969-4cca-8f0e-da3b2a638355",
    "Priority": 10,
    "StartTime": 1487692834.684,
    "EndTime": 1487692835.005,
    "Type": "RUN_COMMAND",
    "TaskParameters": [
        {
            "commands": {
                "Values": [
                    "df"
                ]
            },
            "aws:InstanceId": {
                "Values": [
                    "i-0000293ffd8c57862"
                ]
            }
        }
    ],
    "TaskExecutionId": "ac0c6ae1-daa3-4a89-832e-d384503b6586"
  }


======
Output
======

WindowExecutionId -> (string)

  

  The ID of the Maintenance Window execution that includes the task.

  

  

TaskExecutionId -> (string)

  

  The ID of the specific task execution in the Maintenance Window task that was retrieved.

  

  

TaskArn -> (string)

  

  The ARN of the executed task.

  

  

ServiceRole -> (string)

  

  The role that was assumed when executing the task.

  

  

Type -> (string)

  

  The type of task executed.

  

  

TaskParameters -> (list)

  

  The parameters passed to the task when it was executed. The map has the following format:

   

  Key: string, between 1 and 255 characters

   

  Value: an array of strings, each string is between 1 and 255 characters

  

  (map)

    

    key -> (string)

      

      

    value -> (structure)

      

      Defines the values for a task parameter.

      

      Values -> (list)

        

        This field contains an array of 0 or more strings, each 1 to 255 characters in length.

        

        (string)

          

          

        

      

    

  

Priority -> (integer)

  

  The priority of the task.

  

  

MaxConcurrency -> (string)

  

  The defined maximum number of task executions that could be run in parallel.

  

  

MaxErrors -> (string)

  

  The defined maximum number of task execution errors allowed before scheduling of the task execution would have been stopped.

  

  

Status -> (string)

  

  The status of the task.

  

  

StatusDetails -> (string)

  

  The details explaining the Status. Only available for certain status values.

  

  

StartTime -> (timestamp)

  

  The time the task execution started.

  

  

EndTime -> (timestamp)

  

  The time the task execution completed.

  

  

