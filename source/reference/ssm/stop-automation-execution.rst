[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm stop-automation-execution:


*************************
stop-automation-execution
*************************



===========
Description
===========



Stop an Automation that is currently executing.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/StopAutomationExecution>`_


========
Synopsis
========

::

    stop-automation-execution
  --automation-execution-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--automation-execution-id`` (string)


  The execution ID of the Automation to stop.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To stop the execution of an Automation document**

This example stops an automation execution. There is no output if the command succeeds.

Command::

  aws ssm stop-automation-execution --automation-execution-id "4105a4fc-f944-11e6-9d32-8fb2db27a909"
  

======
Output
======

