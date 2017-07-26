[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-commands:


*************
list-commands
*************



===========
Description
===========



Lists the commands requested by users of the AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/ListCommands>`_


``list-commands`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Commands``


========
Synopsis
========

::

    list-commands
  [--command-id <value>]
  [--instance-id <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--command-id`` (string)


  (Optional) If provided, lists only the specified command.

  

``--instance-id`` (string)


  (Optional) Lists commands issued against this instance ID.

  

``--filters`` (list)


  (Optional) One or more filters. Use a filter to return a more specific list of results. 

  



Shorthand Syntax::

    key=string,value=string ...




JSON Syntax::

  [
    {
      "key": "InvokedAfter"|"InvokedBefore"|"Status",
      "value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list the commands requested by users of an account**

This example lists all commands requested.

Command::

  aws ssm list-commands

Output::

  {
	"Commands": [
		{
			"Comment": "IP config",
			"Status": "Success",
			"MaxErrors": "0",
			"Parameters": {
				"commands": [
					"ifconfig"
				]
			},
			"ExpiresAfter": 1487798019.876,
			"ServiceRole": "",
			"DocumentName": "AWS-RunShellScript",
			"TargetCount": 1,
			"OutputS3BucketName": "",
			"NotificationConfig": {
				"NotificationArn": "",
				"NotificationEvents": [],
				"NotificationType": ""
			},
			"CompletedCount": 1,
			"Targets": [],
			"StatusDetails": "Success",
			"ErrorCount": 0,
			"OutputS3KeyPrefix": "",
			"RequestedDateTime": 1487794419.876,
			"CommandId": "0831e1a8-a1ac-4257-a1fd-c831b48c4107",
			"InstanceIds": [
				"i-0cb2b964d3e14fd9f"
			],
			"MaxConcurrency": "50"
		},
		...
		}
	]
  }

**To get the status of a specific command**

This example gets the status of a command.

Command::

  aws ssm list-commands --command-id "0831e1a8-a1ac-4257-a1fd-c831b48c4107"


======
Output
======

Commands -> (list)

  

  (Optional) The list of commands requested by the user. 

  

  (structure)

    

    Describes a command request.

    

    CommandId -> (string)

      

      A unique identifier for this command.

      

      

    DocumentName -> (string)

      

      The name of the document requested for execution.

      

      

    Comment -> (string)

      

      User-specified information about the command, such as a brief description of what the command should do.

      

      

    ExpiresAfter -> (timestamp)

      

      If this time is reached and the command has not already started executing, it will not execute. Calculated based on the ExpiresAfter user input provided as part of the send-command API.

      

      

    Parameters -> (map)

      

      The parameter values to be inserted in the document when executing the command.

      

      key -> (string)

        

        

      value -> (list)

        

        (string)

          

          

        

      

    InstanceIds -> (list)

      

      The instance IDs against which this command was requested.

      

      (string)

        

        

      

    Targets -> (list)

      

      An array of search criteria that targets instances using a Key,Value combination that you specify. Targets is required if you don't provide one or more instance IDs in the call.

      

      (structure)

        

        An array of search criteria that targets instances using a Key,Value combination that you specify. ``Targets`` is required if you don't provide one or more instance IDs in the call.

         

        

        

        Key -> (string)

          

          User-defined criteria for sending commands that target instances that meet the criteria. Key can be tag:Amazon EC2 tagor InstanceIds. For more information about how to send commands that target instances using Key,Value parameters, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

          

          

        Values -> (list)

          

          User-defined criteria that maps to Key. For example, if you specified tag:ServerRole, you could specify value:WebServer to execute a command on instances that include Amazon EC2 tags of ServerRole,WebServer. For more information about how to send commands that target instances using Key,Value parameters, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

          

          (string)

            

            

          

        

      

    RequestedDateTime -> (timestamp)

      

      The date and time the command was requested.

      

      

    Status -> (string)

      

      The status of the command.

      

      

    StatusDetails -> (string)

      

      A detailed status of the command execution. StatusDetails includes more information than Status because it includes states resulting from error and concurrency control parameters. StatusDetails can show different results than Status. For more information about these statuses, see `Run Command Status <http://docs.aws.amazon.com/systems-manager/latest/userguide/monitor-about-status.html>`_ . StatusDetails can be one of the following values:

       

       
      * Pending: The command has not been sent to any instances. 
       
      * In Progress: The command has been sent to at least one instance but has not reached a final state on all instances. 
       
      * Success: The command successfully executed on all invocations. This is a terminal state. 
       
      * Delivery Timed Out: The value of MaxErrors or more command invocations shows a status of Delivery Timed Out. This is a terminal state. 
       
      * Execution Timed Out: The value of MaxErrors or more command invocations shows a status of Execution Timed Out. This is a terminal state. 
       
      * Failed: The value of MaxErrors or more command invocations shows a status of Failed. This is a terminal state. 
       
      * Incomplete: The command was attempted on all instances and one or more invocations does not have a value of Success but not enough invocations failed for the status to be Failed. This is a terminal state. 
       
      * Canceled: The command was terminated before it was completed. This is a terminal state. 
       
      * Rate Exceeded: The number of instances targeted by the command exceeded the account limit for pending invocations. The system has canceled the command before executing it on any instance. This is a terminal state. 
       

      

      

    OutputS3Region -> (string)

      

      (Deprecated) You can no longer specify this parameter. The system ignores it. Instead, Systems Manager automatically determines the Amazon S3 bucket region.

      

      

    OutputS3BucketName -> (string)

      

      The S3 bucket where the responses to the command executions should be stored. This was requested when issuing the command.

      

      

    OutputS3KeyPrefix -> (string)

      

      The S3 directory path inside the bucket where the responses to the command executions should be stored. This was requested when issuing the command.

      

      

    MaxConcurrency -> (string)

      

      The maximum number of instances that are allowed to execute the command at the same time. You can specify a number of instances, such as 10, or a percentage of instances, such as 10%. The default value is 50. For more information about how to use MaxConcurrency, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/run-command.html>`_ .

      

      

    MaxErrors -> (string)

      

      The maximum number of errors allowed before the system stops sending the command to additional targets. You can specify a number of errors, such as 10, or a percentage or errors, such as 10%. The default value is 50. For more information about how to use MaxErrors, see `Executing a Command Using Systems Manager Run Command <http://docs.aws.amazon.com/systems-manager/latest/userguide/run-command.html>`_ .

      

      

    TargetCount -> (integer)

      

      The number of targets for the command.

      

      

    CompletedCount -> (integer)

      

      The number of targets for which the command invocation reached a terminal state. Terminal states include the following: Success, Failed, Execution Timed Out, Delivery Timed Out, Canceled, Terminated, or Undeliverable.

      

      

    ErrorCount -> (integer)

      

      The number of targets for which the status is Failed or Execution Timed Out.

      

      

    ServiceRole -> (string)

      

      The IAM service role that Run Command uses to act on your behalf when sending notifications about command status changes. 

      

      

    NotificationConfig -> (structure)

      

      Configurations for sending notifications about command status changes. 

      

      NotificationArn -> (string)

        

        An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. Run Command pushes notifications about command status changes to this topic.

        

        

      NotificationEvents -> (list)

        

        The different events for which you can receive notifications. These events include the following: All (events), InProgress, Success, TimedOut, Cancelled, Failed. To learn more about these events, see `Setting Up Events and Notifications <http://docs.aws.amazon.com/systems-manager/latest/userguide/monitor-commands.html>`_ in the *Amazon EC2 Systems Manager User Guide* .

        

        (string)

          

          

        

      NotificationType -> (string)

        

        Command: Receive notification when the status of a command changes. Invocation: For commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. 

        

        

      

    

  

NextToken -> (string)

  

  (Optional) The token for the next set of items to return. (You received this token from a previous call.)

  

  

