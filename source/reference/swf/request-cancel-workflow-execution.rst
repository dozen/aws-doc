[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf request-cancel-workflow-execution:


*********************************
request-cancel-workflow-execution
*********************************



===========
Description
===========



Records a ``WorkflowExecutionCancelRequested`` event in the currently running workflow execution identified by the given domain, workflowId, and runId. This logically requests the cancellation of the workflow execution as a whole. It is up to the decider to take appropriate actions when it receives an execution history with this event.

 

.. note::

  If the runId is not specified, the ``WorkflowExecutionCancelRequested`` event is recorded in the history of the current open workflow execution with the specified workflowId in the domain.

 

.. note::

  Because this action allows the workflow to properly clean up and gracefully close, it should be used instead of  terminate-workflow-execution when possible.

 

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

    request-cancel-workflow-execution
  --domain <value>
  --workflow-id <value>
  [--run-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain containing the workflow execution to cancel.

  

``--workflow-id`` (string)


  The workflowId of the workflow execution to cancel.

  

``--run-id`` (string)


  The runId of the workflow execution to cancel.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
