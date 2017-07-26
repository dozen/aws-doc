[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf signal-workflow-execution:


*************************
signal-workflow-execution
*************************



===========
Description
===========



Records a ``WorkflowExecutionSignaled`` event in the workflow execution history and creates a decision task for the workflow execution identified by the given domain, workflowId and runId. The event is recorded with the specified user defined signalName and input (if provided).

 

.. note::

  If a runId is not specified, then the ``WorkflowExecutionSignaled`` event is recorded in the history of the current open workflow with the matching workflowId in the domain.

 

.. note::

  If the specified workflow execution is not open, this method fails with ``UnknownResource`` .

 

**Access Control** 

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains.
 
* Use an ``Action`` element to allow or deny permission to call this action.
 
* You cannot use an IAM policy to constrain this action's parameters.
 

 

If the caller does not have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's **cause** parameter will be set to OPERATION_NOT_PERMITTED. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .



========
Synopsis
========

::

    signal-workflow-execution
  --domain <value>
  --workflow-id <value>
  [--run-id <value>]
  --signal-name <value>
  [--input <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain containing the workflow execution to signal.

  

``--workflow-id`` (string)


  The workflowId of the workflow execution to signal.

  

``--run-id`` (string)


  The runId of the workflow execution to signal.

  

``--signal-name`` (string)


  The name of the signal. This name must be meaningful to the target workflow.

  

``--input`` (string)


  input to attach to the ``WorkflowExecutionSignaled`` event in the target workflow execution's history.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
