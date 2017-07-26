[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm send-command:


************
send-command
************



===========
Description
===========



Executes commands on one or more managed instances.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/SendCommand>`_


========
Synopsis
========

::

    send-command
  [--instance-ids <value>]
  [--targets <value>]
  --document-name <value>
  [--document-hash <value>]
  [--document-hash-type <value>]
  [--timeout-seconds <value>]
  [--comment <value>]
  [--parameters <value>]
  [--output-s3-region <value>]
  [--output-s3-bucket-name <value>]
  [--output-s3-key-prefix <value>]
  [--max-concurrency <value>]
  [--max-errors <value>]
  [--service-role-arn <value>]
  [--notification-config <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-ids`` (list)


  The instance IDs where the command should execute. You can specify a maximum of 50 IDs. If you prefer not to list individual instance IDs, you can instead send commands to a fleet of instances using the targets parameter, which accepts EC2 tags. For more information about how to use Targets, see `Sending Commands to a Fleet <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

  



Syntax::

  "string" "string" ...



``--targets`` (list)


  (Optional) An array of search criteria that targets instances using a Key,Value combination that you specify. targets is required if you don't provide one or more instance IDs in the call. For more information about how to use Targets, see `Sending Commands to a Fleet <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-multiple.html>`_ .

  



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



``--document-name`` (string)


  Required. The name of the Systems Manager document to execute. This can be a public document or a custom document.

  

``--document-hash`` (string)


  The Sha256 or Sha1 hash created by the system when the document was created. 

   

  .. note::

     

    Sha1 hashes have been deprecated.

     

  

``--document-hash-type`` (string)


  Sha256 or Sha1.

   

  .. note::

     

    Sha1 hashes have been deprecated.

     

  

  Possible values:

  
  *   ``Sha256``

  
  *   ``Sha1``

  

  

``--timeout-seconds`` (integer)


  If this time is reached and the command has not already started executing, it will not execute.

  

``--comment`` (string)


  User-specified information about the command, such as a brief description of what the command should do.

  

``--parameters`` (map)


  The required and optional parameters specified in the document being executed.

  



Shorthand Syntax::

    KeyName1=string,string,KeyName2=string,string




JSON Syntax::

  {"string": ["string", ...]
    ...}



``--output-s3-region`` (string)


  (Deprecated) You can no longer specify this parameter. The system ignores it. Instead, Systems Manager automatically determines the Amazon S3 bucket region.

  

``--output-s3-bucket-name`` (string)


  The name of the S3 bucket where command execution responses should be stored.

  

``--output-s3-key-prefix`` (string)


  The directory structure within the S3 bucket where the responses should be stored.

  

``--max-concurrency`` (string)


  (Optional) The maximum number of instances that are allowed to execute the command at the same time. You can specify a number such as 10 or a percentage such as 10%. The default value is 50. For more information about how to use MaxConcurrency, see `Using Concurrency Controls <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-velocity.html>`_ .

  

``--max-errors`` (string)


  The maximum number of errors allowed without the command failing. When the command fails one more time beyond the value of MaxErrors, the systems stops sending the command to additional targets. You can specify a number like 10 or a percentage like 10%. The default value is 50. For more information about how to use MaxErrors, see `Using Error Controls <http://docs.aws.amazon.com/systems-manager/latest/userguide/send-commands-maxerrors.html>`_ .

  

``--service-role-arn`` (string)


  The IAM role that Systems Manager uses to send notifications. 

  

``--notification-config`` (structure)


  Configurations for sending notifications.

  



Shorthand Syntax::

    NotificationArn=string,NotificationEvents=string,string,NotificationType=string




JSON Syntax::

  {
    "NotificationArn": "string",
    "NotificationEvents": ["All"|"InProgress"|"Success"|"TimedOut"|"Cancelled"|"Failed", ...],
    "NotificationType": "Command"|"Invocation"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To execute a command on one or more remote instances**

This example runs an echo command on a target instance.

Command::

  aws ssm send-command --document-name "AWS-RunPowerShellScript" --parameters commands=["echo helloWorld"] --targets "Key=instanceids,Values=i-0cb2b964d3e14fd9f"
  
Output::

  {
    "Command": {
        "Comment": "",
        "Status": "Pending",
        "MaxErrors": "0",
        "Parameters": {
            "commands": [
                "echo helloWorld"
            ]
        },
        "ExpiresAfter": 1487888845.833,
        "ServiceRole": "",
        "DocumentName": "AWS-RunPowerShellScript",
        "TargetCount": 0,
        "OutputS3BucketName": "",
        "NotificationConfig": {
            "NotificationArn": "",
            "NotificationEvents": [],
            "NotificationType": ""
        },
        "CompletedCount": 0,
        "Targets": [
            {
                "Values": [
                    "i-0cb2b964d3e14fd9f"
                ],
                "Key": "instanceids"
            }
        ],
        "StatusDetails": "Pending",
        "ErrorCount": 0,
        "OutputS3KeyPrefix": "",
        "RequestedDateTime": 1487885245.833,
        "CommandId": "0d4fc863-2154-4e46-990e-d6a952469e91",
        "InstanceIds": [],
        "MaxConcurrency": "50"
    }
  }

**To get IP information about an instance**

This example gets the IP information about an instance.

Command::

  aws ssm send-command --instance-ids "i-0cb2b964d3e14fd9f" --document-name "AWS-RunShellScript" --comment "IP config" --parameters "commands=ifconfig" --output text


======
Output
======

Command -> (structure)

  

  The request as it was received by Systems Manager. Also provides the command ID which can be used future references to this request.

  

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

    

    An array of search criteria that targets instances using a Key,Value combination that you specify. targets is required if you don't provide one or more instance IDs in the call.

    

    (structure)

      

      An array of search criteria that targets instances using a Key,Value combination that you specify. ``targets`` is required if you don't provide one or more instance IDs in the call.

       

      

      

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
     
    * Delivery Timed Out: The value of max-errors or more command invocations shows a status of Delivery Timed Out. This is a terminal state. 
     
    * Execution Timed Out: The value of max-errors or more command invocations shows a status of Execution Timed Out. This is a terminal state. 
     
    * Failed: The value of max-errors or more command invocations shows a status of Failed. This is a terminal state. 
     
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

      

      

    

  

