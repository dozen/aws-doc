[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf terminate-workflow-execution:


****************************
terminate-workflow-execution
****************************



===========
Description
===========



Records a ``WorkflowExecutionTerminated`` event and forces closure of the workflow execution identified by the given domain, runId, and workflowId. The child policy, registered with the workflow type or specified when starting this execution, is applied to any open child workflow executions of this workflow execution.

 

.. warning::

  If the identified workflow execution was in progress, it is terminated immediately.

 

.. note::

  If a runId is not specified, then the ``WorkflowExecutionTerminated`` event is recorded in the history of the current open workflow with the matching workflowId in the domain.

 

.. note::

  You should consider using  request-cancel-workflow-execution action instead because it allows the workflow to gracefully close while  terminate-workflow-execution does not.

 

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

    terminate-workflow-execution
  --domain <value>
  --workflow-id <value>
  [--run-id <value>]
  [--reason <value>]
  [--details <value>]
  [--child-policy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The domain of the workflow execution to terminate.

  

``--workflow-id`` (string)


  The workflowId of the workflow execution to terminate.

  

``--run-id`` (string)


  The runId of the workflow execution to terminate.

  

``--reason`` (string)


  *Optional.* A descriptive reason for terminating the workflow execution.

  

``--details`` (string)


  *Optional.* Details for terminating the workflow execution.

  

``--child-policy`` (string)


  If set, specifies the policy to use for the child workflow executions of the workflow execution being terminated. This policy overrides the child policy specified for the workflow execution at registration time or when starting the execution.

   

  The supported child policies are:

   

   
  * **TERMINATE:** the child executions will be terminated.
   
  * **REQUEST_CANCEL:** a request to cancel will be attempted for each child execution by recording a ``WorkflowExecutionCancelRequested`` event in its history. It is up to the decider to take appropriate actions when it receives an execution history with this event.
   
  * **ABANDON:** no action will be taken. The child executions will continue to run.
   

   

  .. note::

    A child policy for this workflow execution must be specified either as a default for the workflow type or through this parameter. If neither this parameter is set nor a default child policy was specified at registration time then a fault will be returned.

  

  Possible values:

  
  *   ``TERMINATE``

  
  *   ``REQUEST_CANCEL``

  
  *   ``ABANDON``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
