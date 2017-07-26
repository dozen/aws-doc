[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm start-automation-execution:


**************************
start-automation-execution
**************************



===========
Description
===========



Initiates execution of an Automation document.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/StartAutomationExecution>`_


========
Synopsis
========

::

    start-automation-execution
  --document-name <value>
  [--document-version <value>]
  [--parameters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--document-name`` (string)


  The name of the Automation document to use for this execution.

  

``--document-version`` (string)


  The version of the Automation document to use for this execution.

  

``--parameters`` (map)


  A key-value map of execution parameters, which match the declared parameters in the Automation document.

  



Shorthand Syntax::

    KeyName1=string,string,KeyName2=string,string




JSON Syntax::

  {"string": ["string", ...]
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To initiate the execution of an Automation document**

This example executes a document.

Command::

  aws ssm start-automation-execution --document-name "AWS-UpdateLinuxAmi" --parameters "AutomationAssumeRole=arn:aws:iam::812345678901:role/SSMAutomationRole,SourceAmiId=ami-f173cc91,InstanceIamRole=EC2InstanceRole"
  
Output::

  {
	"AutomationExecutionId": "4105a4fc-f944-11e6-9d32-8fb2db27a909"
  }


======
Output
======

AutomationExecutionId -> (string)

  

  The unique ID of a newly scheduled automation execution.

  

  

