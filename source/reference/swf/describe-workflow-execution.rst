[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf describe-workflow-execution:


***************************
describe-workflow-execution
***************************



===========
Description
===========



Returns information about the specified workflow execution including its type and some statistics.

 

.. note::

  This operation is eventually consistent. The results are best effort and may not exactly reflect recent updates and changes.

 

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

    describe-workflow-execution
  --domain <value>
  --execution <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain containing the workflow execution.

  

``--execution`` (structure)


  The workflow execution to describe.

  



Shorthand Syntax::

    workflowId=string,runId=string




JSON Syntax::

  {
    "workflowId": "string",
    "runId": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

executionInfo -> (structure)

  

  Information about the workflow execution.

  

  execution -> (structure)

    

    The workflow execution this information is about.

    

    workflowId -> (string)

      

      The user defined identifier associated with the workflow execution.

      

      

    runId -> (string)

      

      A system-generated unique identifier for the workflow execution.

      

      

    

  workflowType -> (structure)

    

    The type of the workflow execution.

    

    name -> (string)

      

      **Required.** The name of the workflow type.

       

      .. note::

        The combination of workflow type name and version must be unique with in a domain.

      

      

    version -> (string)

      

      **Required.** The version of the workflow type.

       

      .. note::

        The combination of workflow type name and version must be unique with in a domain.

      

      

    

  startTimestamp -> (timestamp)

    

    The time when the execution was started.

    

    

  closeTimestamp -> (timestamp)

    

    The time when the workflow execution was closed. Set only if the execution status is CLOSED.

    

    

  executionStatus -> (string)

    

    The current status of the execution.

    

    

  closeStatus -> (string)

    

    If the execution status is closed then this specifies how the execution was closed:

     

     
    * ``COMPLETED`` : the execution was successfully completed.
     
    * ``CANCELED`` : the execution was canceled.Cancellation allows the implementation to gracefully clean up before the execution is closed.
     
    * ``TERMINATED`` : the execution was force terminated.
     
    * ``FAILED`` : the execution failed to complete.
     
    * ``TIMED_OUT`` : the execution did not complete in the alloted time and was automatically timed out.
     
    * ``CONTINUED_AS_NEW`` : the execution is logically continued. This means the current execution was completed and a new execution was started to carry on the workflow.
     

    

    

  parent -> (structure)

    

    If this workflow execution is a child of another execution then contains the workflow execution that started this execution.

    

    workflowId -> (string)

      

      The user defined identifier associated with the workflow execution.

      

      

    runId -> (string)

      

      A system-generated unique identifier for the workflow execution.

      

      

    

  tagList -> (list)

    

    The list of tags associated with the workflow execution. Tags can be used to identify and list workflow executions of interest through the visibility APIs. A workflow execution can have a maximum of 5 tags.

    

    (string)

      

      

    

  cancelRequested -> (boolean)

    

    Set to true if a cancellation is requested for this workflow execution.

    

    

  

executionConfiguration -> (structure)

  

  The configuration settings for this workflow execution including timeout values, tasklist etc.

  

  taskStartToCloseTimeout -> (string)

    

    The maximum duration allowed for decision tasks for this workflow execution.

     

    The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

    

    

  executionStartToCloseTimeout -> (string)

    

    The total duration for this workflow execution.

     

    The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

    

    

  taskList -> (structure)

    

    The task list used for the decision tasks generated for this workflow execution.

    

    name -> (string)

      

      The name of the task list.

      

      

    

  taskPriority -> (string)

    

    The priority assigned to decision tasks for this workflow execution. Valid values are integers that range from Java's ``Integer.MIN_VALUE`` (-2147483648) to ``Integer.MAX_VALUE`` (2147483647). Higher numbers indicate higher priority.

     

    For more information about setting task priority, see `Setting Task Priority`_ in the *Amazon Simple Workflow Developer Guide* .

    

    

  childPolicy -> (string)

    

    The policy to use for the child workflow executions if this workflow execution is terminated, by calling the  terminate-workflow-execution action explicitly or due to an expired timeout.

     

    The supported child policies are:

     

     
    * **TERMINATE:** the child executions will be terminated.
     
    * **REQUEST_CANCEL:** a request to cancel will be attempted for each child execution by recording a ``WorkflowExecutionCancelRequested`` event in its history. It is up to the decider to take appropriate actions when it receives an execution history with this event.
     
    * **ABANDON:** no action will be taken. The child executions will continue to run.
     

    

    

  lambdaRole -> (string)

    

    The IAM role used by this workflow execution when invoking AWS Lambda functions.

    

    

  

openCounts -> (structure)

  

  The number of tasks for this workflow execution. This includes open and closed tasks of all types.

  

  openActivityTasks -> (integer)

    

    The count of activity tasks whose status is OPEN.

    

    

  openDecisionTasks -> (integer)

    

    The count of decision tasks whose status is OPEN. A workflow execution can have at most one open decision task.

    

    

  openTimers -> (integer)

    

    The count of timers started by this workflow execution that have not fired yet.

    

    

  openChildWorkflowExecutions -> (integer)

    

    The count of child workflow executions whose status is OPEN.

    

    

  openLambdaFunctions -> (integer)

    

    The count of AWS Lambda functions that are currently executing.

    

    

  

latestActivityTaskTimestamp -> (timestamp)

  

  The time when the last activity task was scheduled for this workflow execution. You can use this information to determine if the workflow has not made progress for an unusually long period of time and might require a corrective action.

  

  

latestExecutionContext -> (string)

  

  The latest executionContext provided by the decider for this workflow execution. A decider can provide an executionContext (a free-form string) when closing a decision task using  respond-decision-task-completed .

  

  



.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
.. _Setting Task Priority: http://docs.aws.amazon.com/amazonswf/latest/developerguide/programming-priority.html
