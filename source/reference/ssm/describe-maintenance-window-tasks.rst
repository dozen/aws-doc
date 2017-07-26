[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-maintenance-window-tasks:


*********************************
describe-maintenance-window-tasks
*********************************



===========
Description
===========



Lists the tasks in a Maintenance Window.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeMaintenanceWindowTasks>`_


========
Synopsis
========

::

    describe-maintenance-window-tasks
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


  The ID of the Maintenance Window whose tasks should be retrieved.

  

``--filters`` (list)


  Optional filters used to narrow down the scope of the returned tasks. The supported filter keys are WindowTaskId, TaskArn, Priority, and TaskType.

  



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

**To list all tasks for a Maintenance Window**

This example lists all of the tasks for a maintenance window.

Command::

  aws ssm describe-maintenance-window-tasks --window-id "mw-06cf17cbefcb4bf4f"

Output::

  {
    "Tasks": [
        {
            "ServiceRoleArn": "arn:aws:iam::<aws_account_id>:role/MaintenanceWindowsRole",
            "MaxErrors": "1",
            "TaskArn": "AWS-RunShellScript",
            "MaxConcurrency": "1",
            "WindowTaskId": "a23e338d-ff30-4398-8aa3-09cd052ebf17",
            "TaskParameters": {
                "commands": {
                    "Values": [
                        "df"
                    ]
                }
            },
            "Priority": 10,
            "WindowId": "mw-06cf17cbefcb4bf4f",
            "Type": "RUN_COMMAND",
            "Targets": [
                {
                    "Values": [
                        "i-0000293ffd8c57862"
                    ],
                    "Key": "InstanceIds"
                }
            ]
        }
    ]
  }

**To list all tasks for a maintenance window that invoke the AWS-RunPowerShellScript Run Command**

This example lists all of the tasks for a maintenance window that invoke the ``AWS-RunPowerShellScript`` Run Command.

Command::

  aws ssm describe-maintenance-window-tasks --window-id "mw-ab12cd34ef56gh78" --filters "Key=TaskArn,Values=AWS-RunPowerShellScript"

**To list all tasks for a maintenance window that have a Priority of 3**

This example lists all of the tasks for a maintenance window that have a ``Priority`` of ``3``.

Command::

  aws ssm describe-maintenance-window-tasks --window-id "mw-ab12cd34ef56gh78" --filters "Key=Priority,Values=3"
  
**To list all tasks for a maintenance window that have a Priority of 1 and use Run Command**

This example lists all of the tasks for a maintenance window that have a ``Priority`` of ``1`` and use ``Run Command``.

Command::

  aws ssm describe-maintenance-window-tasks --window-id "mw-ab12cd34ef56gh78" --filters "Key=Priority,Values=1" "Key=TaskType,Values=RUN_COMMAND"

======
Output
======

Tasks -> (list)

  

  Information about the tasks in the Maintenance Window.

  

  (structure)

    

    Information about a task defined for a Maintenance Window.

    

    WindowId -> (string)

      

      The Maintenance Window ID where the task is registered.

      

      

    WindowTaskId -> (string)

      

      The task ID.

      

      

    TaskArn -> (string)

      

      The ARN of the task to execute.

      

      

    Type -> (string)

      

      The type of task.

      

      

    Targets -> (list)

      

      The targets (either instances or tags). Instances are specified using Key=instanceids,Values=instanceid1,instanceid2. Tags are specified using Key=tag name,Values=tag value.

      

      (structure)

        

        An array of search criteria that targets instances using a Key,Value combination that you specify. ``Targets`` is required if you don't provide one or more instance IDs in the call.

         

        

        

        Key -> (string)

          

          User-defined criteria for sending commands that target instances that meet the criteria. Key can be tag:Amazon EC2 tagor InstanceIds. For more information about how to send commands that target instances using Key,Value parameters, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

          

          

        Values -> (list)

          

          User-defined criteria that maps to Key. For example, if you specified tag:ServerRole, you could specify value:WebServer to execute a command on instances that include Amazon EC2 tags of ServerRole,WebServer. For more information about how to send commands that target instances using Key,Value parameters, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

          

          (string)

            

            

          

        

      

    TaskParameters -> (map)

      

      The parameters that should be passed to the task when it is executed.

      

      key -> (string)

        

        

      value -> (structure)

        

        Defines the values for a task parameter.

        

        Values -> (list)

          

          This field contains an array of 0 or more strings, each 1 to 255 characters in length.

          

          (string)

            

            

          

        

      

    Priority -> (integer)

      

      The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.

      

      

    LoggingInfo -> (structure)

      

      Information about an Amazon S3 bucket to write task-level logs to.

      

      S3BucketName -> (string)

        

        The name of an Amazon S3 bucket where execution logs are stored .

        

        

      S3KeyPrefix -> (string)

        

        (Optional) The Amazon S3 bucket subfolder. 

        

        

      S3Region -> (string)

        

        The region where the Amazon S3 bucket is located.

        

        

      

    ServiceRoleArn -> (string)

      

      The role that should be assumed when executing the task

      

      

    MaxConcurrency -> (string)

      

      The maximum number of targets this task can be run for in parallel.

      

      

    MaxErrors -> (string)

      

      The maximum number of errors allowed before this task stops being scheduled.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

