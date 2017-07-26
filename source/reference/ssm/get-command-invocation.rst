[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-command-invocation:


**********************
get-command-invocation
**********************



===========
Description
===========



Returns detailed information about command execution for an invocation or plugin. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetCommandInvocation>`_


========
Synopsis
========

::

    get-command-invocation
  --command-id <value>
  --instance-id <value>
  [--plugin-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--command-id`` (string)


  (Required) The parent command ID of the invocation plugin.

  

``--instance-id`` (string)


  (Required) The ID of the managed instance targeted by the command. A managed instance can be an Amazon EC2 instance or an instance in your hybrid environment that is configured for Systems Manager.

  

``--plugin-name`` (string)


  (Optional) The name of the plugin for which you want detailed results. If the document contains only one plugin, the name can be omitted and the details will be returned.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To display the details of a command invocation**

This example lists all the invocations of a command on an instance.

Command::

  aws ssm get-command-invocation --command-id "bca3371c-3fdf-43f1-9323-7a7780b1b4db" --instance-id "i-0000293ffd8c57862"

Output::

  {
    "Comment": "Apply association with id at creation time: a052fd99-0852-4df2-ad69-0299f2c82047",
    "Status": "SUCCESS",
    "ExecutionEndDateTime": "",
    "StandardErrorContent": "",
    "InstanceId": "i-0000293ffd8c57862",
    "StandardErrorUrl": "",
    "DocumentName": "AWS-RefreshAssociation",
    "StandardOutputContent": "",
    "PluginName": "",
    "ResponseCode": -1,
    "CommandId": "bca3371c-3fdf-43f1-9323-7a7780b1b4db",
    "StandardOutputUrl": ""
  }


======
Output
======

CommandId -> (string)

  

  The parent command ID of the invocation plugin.

  

  

InstanceId -> (string)

  

  The ID of the managed instance targeted by the command. A managed instance can be an Amazon EC2 instance or an instance in your hybrid environment that is configured for Systems Manager.

  

  

Comment -> (string)

  

  The comment text for the command.

  

  

DocumentName -> (string)

  

  The name of the document that was executed. For example, AWS-RunShellScript.

  

  

PluginName -> (string)

  

  The name of the plugin for which you want detailed results. For example, aws:RunShellScript is a plugin.

  

  

ResponseCode -> (integer)

  

  The error level response code for the plugin script. If the response code is -1, then the command has not started executing on the instance, or it was not received by the instance.

  

  

ExecutionStartDateTime -> (string)

  

  The date and time the plugin started executing. Date and time are written in ISO 8601 format. For example, June 7, 2017 is represented as 2017-06-7. The following sample AWS CLI command uses the ``InvokedBefore`` filter.

   

   ``aws ssm list-commands --filters key=InvokedBefore,value=2017-06-07T00:00:00Z``  

   

  If the plugin has not started to execute, the string is empty.

  

  

ExecutionElapsedTime -> (string)

  

  Duration since ExecutionStartDateTime.

  

  

ExecutionEndDateTime -> (string)

  

  The date and time the plugin was finished executing. Date and time are written in ISO 8601 format. For example, June 7, 2017 is represented as 2017-06-7. The following sample AWS CLI command uses the ``InvokedAfter`` filter.

   

   ``aws ssm list-commands --filters key=InvokedAfter,value=2017-06-07T00:00:00Z``  

   

  If the plugin has not started to execute, the string is empty.

  

  

Status -> (string)

  

  The status of the parent command for this invocation. This status can be different than StatusDetails.

  

  

StatusDetails -> (string)

  

  A detailed status of the command execution for an invocation. StatusDetails includes more information than Status because it includes states resulting from error and concurrency control parameters. StatusDetails can show different results than Status. For more information about these statuses, see `Run Command Status <http://docs.aws.amazon.com/systems-manager/latest/userguide/monitor-about-status.html>`_ . StatusDetails can be one of the following values:

   

   
  * Pending: The command has not been sent to the instance. 
   
  * In Progress: The command has been sent to the instance but has not reached a terminal state. 
   
  * Delayed: The system attempted to send the command to the target, but the target was not available. The instance might not be available because of network issues, the instance was stopped, etc. The system will try to deliver the command again. 
   
  * Success: The command or plugin was executed successfully. This is a terminal state. 
   
  * Delivery Timed Out: The command was not delivered to the instance before the delivery timeout expired. Delivery timeouts do not count against the parent command's MaxErrors limit, but they do contribute to whether the parent command status is Success or Incomplete. This is a terminal state. 
   
  * Execution Timed Out: The command started to execute on the instance, but the execution was not complete before the timeout expired. Execution timeouts count against the MaxErrors limit of the parent command. This is a terminal state. 
   
  * Failed: The command wasn't executed successfully on the instance. For a plugin, this indicates that the result code was not zero. For a command invocation, this indicates that the result code for one or more plugins was not zero. Invocation failures count against the MaxErrors limit of the parent command. This is a terminal state. 
   
  * Canceled: The command was terminated before it was completed. This is a terminal state. 
   
  * Undeliverable: The command can't be delivered to the instance. The instance might not exist or might not be responding. Undeliverable invocations don't count against the parent command's MaxErrors limit and don't contribute to whether the parent command status is Success or Incomplete. This is a terminal state. 
   
  * Terminated: The parent command exceeded its MaxErrors limit and subsequent command invocations were canceled by the system. This is a terminal state. 
   

  

  

StandardOutputContent -> (string)

  

  The first 24,000 characters written by the plugin to stdout. If the command has not finished executing, if ExecutionStatus is neither Succeeded nor Failed, then this string is empty.

  

  

StandardOutputUrl -> (string)

  

  The URL for the complete text written by the plugin to stdout in Amazon S3. If an Amazon S3 bucket was not specified, then this string is empty.

  

  

StandardErrorContent -> (string)

  

  The first 8,000 characters written by the plugin to stderr. If the command has not finished executing, then this string is empty.

  

  

StandardErrorUrl -> (string)

  

  The URL for the complete text written by the plugin to stderr. If the command has not finished executing, then this string is empty.

  

  

