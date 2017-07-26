[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-automation-executions:


******************************
describe-automation-executions
******************************



===========
Description
===========



Provides details about all active and terminated Automation executions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeAutomationExecutions>`_


========
Synopsis
========

::

    describe-automation-executions
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  Filters used to limit the scope of executions that are requested.

  



Shorthand Syntax::

    Key=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Key": "DocumentNamePrefix"|"ExecutionStatus",
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

**To get details about all active and terminated Automation executions**

This example displays the details of all Automation Execution.

Command::

  aws ssm describe-automation-executions

Output::

  {
    "AutomationExecutionMetadataList": [
        {
            "AutomationExecutionStatus": "Failed",
            "Outputs": {
                "createImage.ImageId": [
                    "No output available yet because the step is not successfully executed"
                ]
            },
            "DocumentName": "AWS-UpdateLinuxAmi",
            "AutomationExecutionId": "4105a4fc-f944-11e6-9d32-8fb2db27a909",
            "ExecutionEndTime": 1487798228.456,
            "DocumentVersion": "1",
            "ExecutionStartTime": 1487798222.746,
            "ExecutedBy": "admin"
        }
    ]
  }

**To get details of a specific Automation execution**

This example shows the details about a specific Automation Execution.

Command::

   aws ssm get-automation-execution --automation-execution-id "4105a4fc-f944-11e6-9d32-8fb2db27a909"
   

======
Output
======

AutomationExecutionMetadataList -> (list)

  

  The list of details about each automation execution which has occurred which matches the filter specification, if any.

  

  (structure)

    

    Details about a specific Automation execution.

    

    AutomationExecutionId -> (string)

      

      The execution ID.

      

      

    DocumentName -> (string)

      

      The name of the Automation document used during execution.

      

      

    DocumentVersion -> (string)

      

      The document version used during the execution.

      

      

    AutomationExecutionStatus -> (string)

      

      The status of the execution. Valid values include: Running, Succeeded, Failed, Timed out, or Cancelled.

      

      

    ExecutionStartTime -> (timestamp)

      

      The time the execution started.

      

      

    ExecutionEndTime -> (timestamp)

      

      The time the execution finished. This is not populated if the execution is still in progress.

      

      

    ExecutedBy -> (string)

      

      The IAM role ARN of the user who executed the Automation.

      

      

    LogFile -> (string)

      

      An Amazon S3 bucket where execution information is stored.

      

      

    Outputs -> (map)

      

      The list of execution outputs as defined in the Automation document.

      

      key -> (string)

        

        

      value -> (list)

        

        (string)

          

          

        

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

