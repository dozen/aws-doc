[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm register-task-with-maintenance-window:


*************************************
register-task-with-maintenance-window
*************************************



===========
Description
===========



Adds a new task to a Maintenance Window.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/RegisterTaskWithMaintenanceWindow>`_


========
Synopsis
========

::

    register-task-with-maintenance-window
  --window-id <value>
  --targets <value>
  --task-arn <value>
  --service-role-arn <value>
  --task-type <value>
  [--task-parameters <value>]
  [--priority <value>]
  --max-concurrency <value>
  --max-errors <value>
  [--logging-info <value>]
  [--client-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-id`` (string)


  The id of the Maintenance Window the task should be added to.

  

``--targets`` (list)


  The targets (either instances or tags). Instances are specified using Key=instanceids,Values=instanceid1,instanceid2. Tags are specified using Key=tag name,Values=tag value.

  



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



``--task-arn`` (string)


  The ARN of the task to execute 

  

``--service-role-arn`` (string)


  The role that should be assumed when executing the task.

  

``--task-type`` (string)


  The type of task being registered.

  

  Possible values:

  
  *   ``RUN_COMMAND``

  

  

``--task-parameters`` (map)


  The parameters that should be passed to the task when it is executed.

  



Shorthand Syntax::

    KeyName1=Values=string,string,KeyName2=Values=string,string




JSON Syntax::

  {"string": {
        "Values": ["string", ...]
      }
    ...}



``--priority`` (integer)


  The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.

  

``--max-concurrency`` (string)


  The maximum number of targets this task can be run for in parallel.

  

``--max-errors`` (string)


  The maximum number of errors allowed before this task stops being scheduled.

  

``--logging-info`` (structure)


  A structure containing information about an Amazon S3 bucket to write instance-level logs to. 

  



Shorthand Syntax::

    S3BucketName=string,S3KeyPrefix=string,S3Region=string




JSON Syntax::

  {
    "S3BucketName": "string",
    "S3KeyPrefix": "string",
    "S3Region": "string"
  }



``--client-token`` (string)


  User-provided idempotency token.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To register a task with a maintenance window**

This example registers a task to a maintenance window which is targeted at an instance.

Command::

  aws ssm register-task-with-maintenance-window --window-id "mw-ab12cd34ef56gh78" --task-arn "AWS-RunShellScript" --targets "Key=InstanceIds,Values=i-0000293ffd8c57862" --service-role-arn "arn:aws:iam::812345678901:role/MaintenanceWindowsRole" --task-type "RUN_COMMAND" --task-parameters "{\"commands\":{\"Values\":[\"df\"]}}" --max-concurrency 1 --max-errors 1 --priority 10
  
Output::

  {
	"WindowTaskId":"44444444-5555-6666-7777-88888888"
  }
	
**To register a task using a Maintenance Windows target ID**
	
This example registers a task using a maintenance window target ID. The maintenance window target ID was in the output of the ``aws ssm register-target-with-maintenance-window`` command, otherwise you can retrieve it from the output of the ``aws ssm describe-maintenance-window-targets`` command.

Command::

  aws ssm register-task-with-maintenance-window --targets "Key=WindowTargetIds,Values=350d44e6-28cc-44e2-951f-4b2c985838f6" --task-arn "AWS-RunShellScript" --service-role-arn "arn:aws:iam::812345678901:role/MaintenanceWindowsRole" --window-id "mw-ab12cd34ef56gh78" --task-type "RUN_COMMAND" --task-parameters  "{\"commands\":{\"Values\":[\"df\"]}}" --max-concurrency 1 --max-errors 1 --priority 10
  

======
Output
======

WindowTaskId -> (string)

  

  The id of the task in the Maintenance Window.

  

  

