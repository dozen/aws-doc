[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-command-invocations:


************************
list-command-invocations
************************



===========
Description
===========



An invocation is copy of a command sent to a specific instance. A command can apply to one or more instances. A command invocation applies to one instance. For example, if a user executes send-command against three instances, then a command invocation is created for each requested instance ID. list-command-invocations provide status about command execution.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/ListCommandInvocations>`_


``list-command-invocations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CommandInvocations``


========
Synopsis
========

::

    list-command-invocations
  [--command-id <value>]
  [--instance-id <value>]
  [--filters <value>]
  [--details | --no-details]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--command-id`` (string)


  (Optional) The invocations for a specific command ID.

  

``--instance-id`` (string)


  (Optional) The command execution details for a specific instance ID.

  

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



``--details`` | ``--no-details`` (boolean)


  (Optional) If set this returns the response of the command executions and any command output. By default this is set to False. 

  

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

**To list the invocations of a specific command**

This example lists all the invocations of a command.

Command::

  aws ssm list-command-invocations --command-id "b8eac879-0541-439d-94ec-47a80d554f44" --details

Output::

  {
	"CommandInvocations": [
		{
			"Comment": "IP config",
			"Status": "Success",
			"CommandPlugins": [
				{
					"Status": "Success",
					"ResponseStartDateTime": 1487794396.651,
					"StandardErrorUrl": "",
					"OutputS3BucketName": "",
					"OutputS3Region": "us-west-2",
					"OutputS3KeyPrefix": "",
					"ResponseCode": 0,
					"Output": "eth0      Link encap:Ethernet  HWaddr 06:41:38:F5:D6:EF  \n          inet addr:172.31.44.222  Bcast:172.31.47.255  Mask:255.255.240.0\n          inet6 addr: fe80::441:38ff:fef5:d6ef/64 Scope:Link\n          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1\n          RX packets:186705 errors:0 dropped:0 overruns:0 frame:0\n          TX packets:188811 errors:0 dropped:0 overruns:0 carrier:0\n          collisions:0 txqueuelen:1000 \n          RX bytes:91749280 (87.4 MiB)  TX bytes:31721645 (30.2 MiB)\n\nlo        Link encap:Local Loopback  \n          inet addr:127.0.0.1  Mask:255.0.0.0\n         inet6 addr: ::1/128 Scope:Host\n          UP LOOPBACK RUNNING  MTU:65536  Metric:1\n          RX packets:2 errors:0 dropped:0 overruns:0 frame:0\n          X packets:2 errors:0 dropped:0 overruns:0 carrier:0\n          collisions:0 txqueuelen:1 \n          RX bytes:140 (140.0 b)  TX bytes:140 (140.0 b)\n\n",
					"ResponseFinishDateTime": 1487794396.655,
					"StatusDetails": "Success",
					"StandardOutputUrl": "",
					"Name": "aws:runShellScript"
				}
			],
			"ServiceRole": "",
			"InstanceId": "i-0cb2b964d3e14fd9f",
			"DocumentName": "AWS-RunShellScript",
			"NotificationConfig": {
				"NotificationArn": "",
				"NotificationEvents": [],
				"NotificationType": ""
			},
			"StatusDetails": "Success",
			"StandardOutputUrl": "",
			"StandardErrorUrl": "",
			"InstanceName": "",
			"CommandId": "b8eac879-0541-439d-94ec-47a80d554f44",
			"RequestedDateTime": 1487794396.363
		}
	]
  }


======
Output
======

CommandInvocations -> (list)

  

  (Optional) A list of all invocations. 

  

  (structure)

    

    An invocation is copy of a command sent to a specific instance. A command can apply to one or more instances. A command invocation applies to one instance. For example, if a user executes send-command against three instances, then a command invocation is created for each requested instance ID. A command invocation returns status and detail information about a command you executed. 

    

    CommandId -> (string)

      

      The command against which this invocation was requested.

      

      

    InstanceId -> (string)

      

      The instance ID in which this invocation was requested.

      

      

    InstanceName -> (string)

      

      The name of the invocation target. For Amazon EC2 instances this is the value for the aws:Name tag. For on-premises instances, this is the name of the instance.

      

      

    Comment -> (string)

      

      User-specified information about the command, such as a brief description of what the command should do.

      

      

    DocumentName -> (string)

      

      The document name that was requested for execution.

      

      

    RequestedDateTime -> (timestamp)

      

      The time and date the request was sent to this instance.

      

      

    Status -> (string)

      

      Whether or not the invocation succeeded, failed, or is pending.

      

      

    StatusDetails -> (string)

      

      A detailed status of the command execution for each invocation (each instance targeted by the command). StatusDetails includes more information than Status because it includes states resulting from error and concurrency control parameters. StatusDetails can show different results than Status. For more information about these statuses, see `Run Command Status <http://docs.aws.amazon.com/systems-manager/latest/userguide/monitor-about-status.html>`_ . StatusDetails can be one of the following values:

       

       
      * Pending: The command has not been sent to the instance. 
       
      * In Progress: The command has been sent to the instance but has not reached a terminal state. 
       
      * Success: The execution of the command or plugin was successfully completed. This is a terminal state. 
       
      * Delivery Timed Out: The command was not delivered to the instance before the delivery timeout expired. Delivery timeouts do not count against the parent command's MaxErrors limit, but they do contribute to whether the parent command status is Success or Incomplete. This is a terminal state. 
       
      * Execution Timed Out: Command execution started on the instance, but the execution was not complete before the execution timeout expired. Execution timeouts count against the MaxErrors limit of the parent command. This is a terminal state. 
       
      * Failed: The command was not successful on the instance. For a plugin, this indicates that the result code was not zero. For a command invocation, this indicates that the result code for one or more plugins was not zero. Invocation failures count against the MaxErrors limit of the parent command. This is a terminal state. 
       
      * Canceled: The command was terminated before it was completed. This is a terminal state. 
       
      * Undeliverable: The command can't be delivered to the instance. The instance might not exist or might not be responding. Undeliverable invocations don't count against the parent command's MaxErrors limit and don't contribute to whether the parent command status is Success or Incomplete. This is a terminal state. 
       
      * Terminated: The parent command exceeded its MaxErrors limit and subsequent command invocations were canceled by the system. This is a terminal state. 
       

      

      

    TraceOutput -> (string)

      

      Gets the trace output sent by the agent. 

      

      

    StandardOutputUrl -> (string)

      

      The URL to the plugin's StdOut file in Amazon S3, if the Amazon S3 bucket was defined for the parent command. For an invocation, StandardOutputUrl is populated if there is just one plugin defined for the command, and the Amazon S3 bucket was defined for the command.

      

      

    StandardErrorUrl -> (string)

      

      The URL to the plugin's StdErr file in Amazon S3, if the Amazon S3 bucket was defined for the parent command. For an invocation, StandardErrorUrl is populated if there is just one plugin defined for the command, and the Amazon S3 bucket was defined for the command.

      

      

    CommandPlugins -> (list)

      

      (structure)

        

        Describes plugin details.

        

        Name -> (string)

          

          The name of the plugin. Must be one of the following: aws:updateAgent, aws:domainjoin, aws:applications, aws:runPowerShellScript, aws:psmodule, aws:cloudWatch, aws:runShellScript, or aws:updateSSMAgent. 

          

          

        Status -> (string)

          

          The status of this plugin. You can execute a document with multiple plugins.

          

          

        StatusDetails -> (string)

          

          A detailed status of the plugin execution. StatusDetails includes more information than Status because it includes states resulting from error and concurrency control parameters. StatusDetails can show different results than Status. For more information about these statuses, see `Run Command Status <http://docs.aws.amazon.com/systems-manager/latest/userguide/monitor-about-status.html>`_ . StatusDetails can be one of the following values:

           

           
          * Pending: The command has not been sent to the instance. 
           
          * In Progress: The command has been sent to the instance but has not reached a terminal state. 
           
          * Success: The execution of the command or plugin was successfully completed. This is a terminal state. 
           
          * Delivery Timed Out: The command was not delivered to the instance before the delivery timeout expired. Delivery timeouts do not count against the parent command's MaxErrors limit, but they do contribute to whether the parent command status is Success or Incomplete. This is a terminal state. 
           
          * Execution Timed Out: Command execution started on the instance, but the execution was not complete before the execution timeout expired. Execution timeouts count against the MaxErrors limit of the parent command. This is a terminal state. 
           
          * Failed: The command was not successful on the instance. For a plugin, this indicates that the result code was not zero. For a command invocation, this indicates that the result code for one or more plugins was not zero. Invocation failures count against the MaxErrors limit of the parent command. This is a terminal state. 
           
          * Canceled: The command was terminated before it was completed. This is a terminal state. 
           
          * Undeliverable: The command can't be delivered to the instance. The instance might not exist, or it might not be responding. Undeliverable invocations don't count against the parent command's MaxErrors limit, and they don't contribute to whether the parent command status is Success or Incomplete. This is a terminal state. 
           
          * Terminated: The parent command exceeded its MaxErrors limit and subsequent command invocations were canceled by the system. This is a terminal state. 
           

          

          

        ResponseCode -> (integer)

          

          A numeric response code generated after executing the plugin. 

          

          

        ResponseStartDateTime -> (timestamp)

          

          The time the plugin started executing. 

          

          

        ResponseFinishDateTime -> (timestamp)

          

          The time the plugin stopped executing. Could stop prematurely if, for example, a cancel command was sent. 

          

          

        Output -> (string)

          

          Output of the plugin execution.

          

          

        StandardOutputUrl -> (string)

          

          The URL for the complete text written by the plugin to stdout in Amazon S3. If the Amazon S3 bucket for the command was not specified, then this string is empty.

          

          

        StandardErrorUrl -> (string)

          

          The URL for the complete text written by the plugin to stderr. If execution is not yet complete, then this string is empty.

          

          

        OutputS3Region -> (string)

          

          (Deprecated) You can no longer specify this parameter. The system ignores it. Instead, Systems Manager automatically determines the Amazon S3 bucket region.

          

          

        OutputS3BucketName -> (string)

          

          The S3 bucket where the responses to the command executions should be stored. This was requested when issuing the command. For example, in the following response:

           

          test_folder/ab19cb99-a030-46dd-9dfc-8eSAMPLEPre-Fix/i-1234567876543/awsrunShellScript 

           

          test_folder is the name of the Amazon S3 bucket;

           

          ab19cb99-a030-46dd-9dfc-8eSAMPLEPre-Fix is the name of the S3 prefix;

           

          i-1234567876543 is the instance ID;

           

          awsrunShellScript is the name of the plugin.

          

          

        OutputS3KeyPrefix -> (string)

          

          The S3 directory path inside the bucket where the responses to the command executions should be stored. This was requested when issuing the command. For example, in the following response:

           

          test_folder/ab19cb99-a030-46dd-9dfc-8eSAMPLEPre-Fix/i-1234567876543/awsrunShellScript 

           

          test_folder is the name of the Amazon S3 bucket;

           

          ab19cb99-a030-46dd-9dfc-8eSAMPLEPre-Fix is the name of the S3 prefix;

           

          i-1234567876543 is the instance ID;

           

          awsrunShellScript is the name of the plugin.

          

          

        

      

    ServiceRole -> (string)

      

      The IAM service role that Run Command uses to act on your behalf when sending notifications about command status changes on a per instance basis.

      

      

    NotificationConfig -> (structure)

      

      Configurations for sending notifications about command status changes on a per instance basis.

      

      NotificationArn -> (string)

        

        An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. Run Command pushes notifications about command status changes to this topic.

        

        

      NotificationEvents -> (list)

        

        The different events for which you can receive notifications. These events include the following: All (events), InProgress, Success, TimedOut, Cancelled, Failed. To learn more about these events, see `Setting Up Events and Notifications <http://docs.aws.amazon.com/systems-manager/latest/userguide/monitor-commands.html>`_ in the *Amazon EC2 Systems Manager User Guide* .

        

        (string)

          

          

        

      NotificationType -> (string)

        

        Command: Receive notification when the status of a command changes. Invocation: For commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. 

        

        

      

    

  

NextToken -> (string)

  

  (Optional) The token for the next set of items to return. (You received this token from a previous call.)

  

  

