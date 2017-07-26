[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-automation-execution:


************************
get-automation-execution
************************



===========
Description
===========



Get detailed information about a particular Automation execution.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetAutomationExecution>`_


========
Synopsis
========

::

    get-automation-execution
  --automation-execution-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--automation-execution-id`` (string)


  The unique identifier for an existing automation execution to examine. The execution ID is returned by start-automation-execution when the execution of an Automation document is initiated.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To display the details of an Automation Execution**

This example displays the details of an Automation Execution.

Command::

  aws ssm get-automation-execution --automation-execution-id "4105a4fc-f944-11e6-9d32-8fb2db27a909"

Output::

  {
    "AutomationExecution": {
        "AutomationExecutionStatus": "Failed",
        "Parameters": {
            "SourceAmiId": [
                "ami-f173cc91"
            ],
            "AutomationAssumeRole": [
                "arn:aws:iam::812345678901:role/SSMAutomationRole"
            ],
            "InstanceIamRole": [
                "EC2InstanceRole"
            ]
        },
        "Outputs": {
            "createImage.ImageId": [
                "No output available yet because the step is not successfully executed"
            ]
        },
        "DocumentName": "AWS-UpdateLinuxAmi",
        "AutomationExecutionId": "4105a4fc-f944-11e6-9d32-8fb2db27a909",
        "FailureMessage": "Step launchInstance failed maximum allowed times. You are not authorized to perform this operation. Encoded authorization failure message: --truncated-- (Service: AmazonEC2; Status Code: 403; Error Code: UnauthorizedOperation; Request ID: 6a002f94-ba37-43fd-99e6-39517715fce5)",
        "ExecutionEndTime": 1487798228.456,
        "DocumentVersion": "1",
        "ExecutionStartTime": 1487798222.746,
        "StepExecutions": [
            {
                "Inputs": {
                    "MaxInstanceCount": "1",
                    "UserData": "\"--truncated--\"",
                    "MinInstanceCount": "1",
                    "ImageId": "\"ami-f173cc91\"",
                    "IamInstanceProfileName": "\"EC2InstanceRole\"",
                    "InstanceType": "\"t2.micro\""
                },
                "StepName": "launchInstance",
                "FailureMessage": "Step launchInstance failed maximum allowed times. You are not authorized to perform this operation. Encoded authorization failure message: --truncated--)",
                "ExecutionEndTime": 1487798226.014,
                "ExecutionStartTime": 1487798223.346,
                "Action": "aws:runInstances",
                "StepStatus": "Failed"
            },
            {
                "Action": "aws:runCommand",
                "StepName": "updateOSSoftware",
                "StepStatus": "Pending"
            },
            {
                "Action": "aws:changeInstanceState",
                "StepName": "stopInstance",
                "StepStatus": "Pending"
            },
            {
                "Action": "aws:createImage",
                "StepName": "createImage",
                "StepStatus": "Pending"
            },
            {
                "Action": "aws:changeInstanceState",
                "StepName": "terminateInstance",
                "StepStatus": "Pending"
            }
        ]
    }
  }
  

======
Output
======

AutomationExecution -> (structure)

  

  Detailed information about the current state of an automation execution.

  

  AutomationExecutionId -> (string)

    

    The execution ID.

    

    

  DocumentName -> (string)

    

    The name of the Automation document used during the execution.

    

    

  DocumentVersion -> (string)

    

    The version of the document to use during execution.

    

    

  ExecutionStartTime -> (timestamp)

    

    The time the execution started.

    

    

  ExecutionEndTime -> (timestamp)

    

    The time the execution finished.

    

    

  AutomationExecutionStatus -> (string)

    

    The execution status of the Automation.

    

    

  StepExecutions -> (list)

    

    A list of details about the current state of all steps that comprise an execution. An Automation document contains a list of steps that are executed in order.

    

    (structure)

      

      Detailed information about an the execution state of an Automation step.

      

      StepName -> (string)

        

        The name of this execution step.

        

        

      Action -> (string)

        

        The action this step performs. The action determines the behavior of the step.

        

        

      ExecutionStartTime -> (timestamp)

        

        If a step has begun execution, this contains the time the step started. If the step is in Pending status, this field is not populated.

        

        

      ExecutionEndTime -> (timestamp)

        

        If a step has finished execution, this contains the time the execution ended. If the step has not yet concluded, this field is not populated.

        

        

      StepStatus -> (string)

        

        The execution status for this step. Valid values include: Pending, InProgress, Success, Cancelled, Failed, and TimedOut.

        

        

      ResponseCode -> (string)

        

        The response code returned by the execution of the step.

        

        

      Inputs -> (map)

        

        Fully-resolved values passed into the step before execution.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      Outputs -> (map)

        

        Returned values from the execution of the step.

        

        key -> (string)

          

          

        value -> (list)

          

          (string)

            

            

          

        

      Response -> (string)

        

        A message associated with the response code for an execution.

        

        

      FailureMessage -> (string)

        

        If a step failed, this message explains why the execution failed.

        

        

      FailureDetails -> (structure)

        

        Information about the Automation failure.

        

        FailureStage -> (string)

          

          The stage of the Automation execution when the failure occurred. The stages include the following: InputValidation, PreVerification, Invocation, PostVerification.

          

          

        FailureType -> (string)

          

          The type of Automation failure. Failure types include the following: Action, Permission, Throttling, Verification, Internal.

          

          

        Details -> (map)

          

          Detailed information about the Automation step failure.

          

          key -> (string)

            

            

          value -> (list)

            

            (string)

              

              

            

          

        

      

    

  Parameters -> (map)

    

    The key-value map of execution parameters, which were supplied when calling StartAutomationExecution.

    

    key -> (string)

      

      

    value -> (list)

      

      (string)

        

        

      

    

  Outputs -> (map)

    

    The list of execution outputs as defined in the automation document.

    

    key -> (string)

      

      

    value -> (list)

      

      (string)

        

        

      

    

  FailureMessage -> (string)

    

    A message describing why an execution has failed, if the status is set to Failed.

    

    

  

