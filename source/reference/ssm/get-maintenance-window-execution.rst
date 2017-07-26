[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-maintenance-window-execution:


********************************
get-maintenance-window-execution
********************************



===========
Description
===========



Retrieves details about a specific task executed as part of a Maintenance Window execution.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetMaintenanceWindowExecution>`_


========
Synopsis
========

::

    get-maintenance-window-execution
  --window-execution-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-execution-id`` (string)


  The ID of the Maintenance Window execution that includes the task.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about a Maintenance Window task execution**

This example lists information about a task executed as part of a maintenance window execution.

Command::

  aws ssm get-maintenance-window-execution --window-execution-id "518d5565-5969-4cca-8f0e-da3b2a638355"

Output::

  {
    "Status": "SUCCESS",
    "TaskIds": [
        "ac0c6ae1-daa3-4a89-832e-d384503b6586"
    ],
    "StartTime": 1487692834.595,
    "EndTime": 1487692835.051,
    "WindowExecutionId": "518d5565-5969-4cca-8f0e-da3b2a638355",
  }


======
Output
======

WindowExecutionId -> (string)

  

  The ID of the Maintenance Window execution.

  

  

TaskIds -> (list)

  

  The ID of the task executions from the Maintenance Window execution.

  

  (string)

    

    

  

Status -> (string)

  

  The status of the Maintenance Window execution.

  

  

StatusDetails -> (string)

  

  The details explaining the Status. Only available for certain status values.

  

  

StartTime -> (timestamp)

  

  The time the Maintenance Window started executing.

  

  

EndTime -> (timestamp)

  

  The time the Maintenance Window finished executing.

  

  

