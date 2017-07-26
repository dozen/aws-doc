[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf get-workflow-execution-history:


******************************
get-workflow-execution-history
******************************



===========
Description
===========



Returns the history of the specified workflow execution. The results may be split into multiple pages. To retrieve subsequent pages, make the call again using the ``nextPageToken`` returned by the initial call.

 

.. note::

  This operation is eventually consistent. The results are best effort and may not exactly reflect recent updates and changes.

 

**Access Control** 

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains.
 
* Use an ``Action`` element to allow or deny permission to call this action.
 
* You cannot use an IAM policy to constrain this action's parameters.
 

 

If the caller does not have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's **cause** parameter will be set to OPERATION_NOT_PERMITTED. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .



``get-workflow-execution-history`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``events``


========
Synopsis
========

::

    get-workflow-execution-history
  --domain <value>
  --execution <value>
  [--reverse-order | --no-reverse-order]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain containing the workflow execution.

  

``--execution`` (structure)


  Specifies the workflow execution for which to return the history.

  



Shorthand Syntax::

    workflowId=string,runId=string




JSON Syntax::

  {
    "workflowId": "string",
    "runId": "string"
  }



``--reverse-order`` | ``--no-reverse-order`` (boolean)


  When set to ``true`` , returns the events in reverse order. By default the results are returned in ascending order of the ``eventTimeStamp`` of the events.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

events -> (list)

  

  The list of history events.

  

  (structure)

    

    Event within a workflow execution. A history event can be one of these types:

     

     
    * **WorkflowExecutionStarted** : The workflow execution was started.
     
    * **WorkflowExecutionCompleted** : The workflow execution was closed due to successful completion.
     
    * **WorkflowExecutionFailed** : The workflow execution closed due to a failure.
     
    * **WorkflowExecutionTimedOut** : The workflow execution was closed because a time out was exceeded.
     
    * **WorkflowExecutionCanceled** : The workflow execution was successfully canceled and closed.
     
    * **WorkflowExecutionTerminated** : The workflow execution was terminated.
     
    * **WorkflowExecutionContinuedAsNew** : The workflow execution was closed and a new execution of the same type was created with the same workflowId.
     
    * **WorkflowExecutionCancelRequested** : A request to cancel this workflow execution was made.
     
    * **DecisionTaskScheduled** : A decision task was scheduled for the workflow execution.
     
    * **DecisionTaskStarted** : The decision task was dispatched to a decider.
     
    * **DecisionTaskCompleted** : The decider successfully completed a decision task by calling  respond-decision-task-completed .
     
    * **DecisionTaskTimedOut** : The decision task timed out.
     
    * **ActivityTaskScheduled** : An activity task was scheduled for execution.
     
    * **ScheduleActivityTaskFailed** : Failed to process ScheduleActivityTask decision. This happens when the decision is not configured properly, for example the activity type specified is not registered.
     
    * **ActivityTaskStarted** : The scheduled activity task was dispatched to a worker.
     
    * **ActivityTaskCompleted** : An activity worker successfully completed an activity task by calling  respond-activity-task-completed .
     
    * **ActivityTaskFailed** : An activity worker failed an activity task by calling  respond-activity-task-failed .
     
    * **ActivityTaskTimedOut** : The activity task timed out.
     
    * **ActivityTaskCanceled** : The activity task was successfully canceled.
     
    * **ActivityTaskCancelRequested** : A ``RequestCancelActivityTask`` decision was received by the system.
     
    * **RequestCancelActivityTaskFailed** : Failed to process RequestCancelActivityTask decision. This happens when the decision is not configured properly.
     
    * **WorkflowExecutionSignaled** : An external signal was received for the workflow execution.
     
    * **MarkerRecorded** : A marker was recorded in the workflow history as the result of a ``RecordMarker`` decision.
     
    * **TimerStarted** : A timer was started for the workflow execution due to a ``StartTimer`` decision.
     
    * **StartTimerFailed** : Failed to process StartTimer decision. This happens when the decision is not configured properly, for example a timer already exists with the specified timer ID.
     
    * **TimerFired** : A timer, previously started for this workflow execution, fired.
     
    * **TimerCanceled** : A timer, previously started for this workflow execution, was successfully canceled.
     
    * **CancelTimerFailed** : Failed to process CancelTimer decision. This happens when the decision is not configured properly, for example no timer exists with the specified timer ID.
     
    * **StartChildWorkflowExecutionInitiated** : A request was made to start a child workflow execution.
     
    * **StartChildWorkflowExecutionFailed** : Failed to process StartChildWorkflowExecution decision. This happens when the decision is not configured properly, for example the workflow type specified is not registered.
     
    * **ChildWorkflowExecutionStarted** : A child workflow execution was successfully started.
     
    * **ChildWorkflowExecutionCompleted** : A child workflow execution, started by this workflow execution, completed successfully and was closed.
     
    * **ChildWorkflowExecutionFailed** : A child workflow execution, started by this workflow execution, failed to complete successfully and was closed.
     
    * **ChildWorkflowExecutionTimedOut** : A child workflow execution, started by this workflow execution, timed out and was closed.
     
    * **ChildWorkflowExecutionCanceled** : A child workflow execution, started by this workflow execution, was canceled and closed.
     
    * **ChildWorkflowExecutionTerminated** : A child workflow execution, started by this workflow execution, was terminated.
     
    * **SignalExternalWorkflowExecutionInitiated** : A request to signal an external workflow was made.
     
    * **ExternalWorkflowExecutionSignaled** : A signal, requested by this workflow execution, was successfully delivered to the target external workflow execution.
     
    * **SignalExternalWorkflowExecutionFailed** : The request to signal an external workflow execution failed.
     
    * **RequestCancelExternalWorkflowExecutionInitiated** : A request was made to request the cancellation of an external workflow execution.
     
    * **ExternalWorkflowExecutionCancelRequested** : Request to cancel an external workflow execution was successfully delivered to the target execution.
     
    * **RequestCancelExternalWorkflowExecutionFailed** : Request to cancel an external workflow execution failed.
     
    * **LambdaFunctionScheduled** : An AWS Lambda function was scheduled for execution.
     
    * **LambdaFunctionStarted** : The scheduled function was invoked in the AWS Lambda service.
     
    * **LambdaFunctionCompleted** : The AWS Lambda function successfully completed.
     
    * **LambdaFunctionFailed** : The AWS Lambda function execution failed.
     
    * **LambdaFunctionTimedOut** : The AWS Lambda function execution timed out.
     
    * **ScheduleLambdaFunctionFailed** : Failed to process ScheduleLambdaFunction decision. This happens when the workflow execution does not have the proper IAM role attached to invoke AWS Lambda functions.
     
    * **StartLambdaFunctionFailed** : Failed to invoke the scheduled function in the AWS Lambda service. This happens when the AWS Lambda service is not available in the current region, or received too many requests.
     

    

    eventTimestamp -> (timestamp)

      

      The date and time when the event occurred.

      

      

    eventType -> (string)

      

      The type of the history event.

      

      

    eventId -> (long)

      

      The system generated ID of the event. This ID uniquely identifies the event with in the workflow execution history.

      

      

    workflowExecutionStartedEventAttributes -> (structure)

      

      If the event is of type ``WorkflowExecutionStarted`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      input -> (string)

        

        The input provided to the workflow execution (if any).

        

        

      executionStartToCloseTimeout -> (string)

        

        The maximum duration for this workflow execution.

         

        The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

        

        

      taskStartToCloseTimeout -> (string)

        

        The maximum duration of decision tasks for this workflow type.

         

        The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

        

        

      childPolicy -> (string)

        

        The policy to use for the child workflow executions if this workflow execution is terminated, by calling the  terminate-workflow-execution action explicitly or due to an expired timeout.

         

        The supported child policies are:

         

         
        * **TERMINATE:** the child executions will be terminated.
         
        * **REQUEST_CANCEL:** a request to cancel will be attempted for each child execution by recording a ``WorkflowExecutionCancelRequested`` event in its history. It is up to the decider to take appropriate actions when it receives an execution history with this event.
         
        * **ABANDON:** no action will be taken. The child executions will continue to run.
         

        

        

      taskList -> (structure)

        

        The name of the task list for scheduling the decision tasks for this workflow execution.

        

        name -> (string)

          

          The name of the task list.

          

          

        

      workflowType -> (structure)

        

        The workflow type of this execution.

        

        name -> (string)

          

          **Required.** The name of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        version -> (string)

          

          **Required.** The version of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        

      tagList -> (list)

        

        The list of tags associated with this workflow execution. An execution can have up to 5 tags.

        

        (string)

          

          

        

      taskPriority -> (string)

        

        

      continuedExecutionRunId -> (string)

        

        If this workflow execution was started due to a ``ContinueAsNewWorkflowExecution`` decision, then it contains the ``runId`` of the previous workflow execution that was closed and continued as this execution.

        

        

      parentWorkflowExecution -> (structure)

        

        The source workflow execution that started this workflow execution. The member is not set if the workflow execution was not started by a workflow.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      parentInitiatedEventId -> (long)

        

        The ID of the ``StartChildWorkflowExecutionInitiated`` event corresponding to the ``StartChildWorkflowExecution`` decision to start this workflow execution. The source event with this ID can be found in the history of the source workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      lambdaRole -> (string)

        

        The IAM role attached to this workflow execution to use when invoking AWS Lambda functions.

        

        

      

    workflowExecutionCompletedEventAttributes -> (structure)

      

      If the event is of type ``WorkflowExecutionCompleted`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      result -> (string)

        

        The result produced by the workflow execution upon successful completion.

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``CompleteWorkflowExecution`` decision to complete this execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    completeWorkflowExecutionFailedEventAttributes -> (structure)

      

      If the event is of type ``CompleteWorkflowExecutionFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``CompleteWorkflowExecution`` decision to complete this execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    workflowExecutionFailedEventAttributes -> (structure)

      

      If the event is of type ``WorkflowExecutionFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      reason -> (string)

        

        The descriptive reason provided for the failure (if any).

        

        

      details -> (string)

        

        The details of the failure (if any).

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``FailWorkflowExecution`` decision to fail this execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    failWorkflowExecutionFailedEventAttributes -> (structure)

      

      If the event is of type ``FailWorkflowExecutionFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``FailWorkflowExecution`` decision to fail this execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    workflowExecutionTimedOutEventAttributes -> (structure)

      

      If the event is of type ``WorkflowExecutionTimedOut`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      timeoutType -> (string)

        

        The type of timeout that caused this event.

        

        

      childPolicy -> (string)

        

        The policy used for the child workflow executions of this workflow execution.

         

        The supported child policies are:

         

         
        * **TERMINATE:** the child executions will be terminated.
         
        * **REQUEST_CANCEL:** a request to cancel will be attempted for each child execution by recording a ``WorkflowExecutionCancelRequested`` event in its history. It is up to the decider to take appropriate actions when it receives an execution history with this event.
         
        * **ABANDON:** no action will be taken. The child executions will continue to run.
         

        

        

      

    workflowExecutionCanceledEventAttributes -> (structure)

      

      If the event is of type ``WorkflowExecutionCanceled`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      details -> (string)

        

        Details for the cancellation (if any).

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``CancelWorkflowExecution`` decision for this cancellation request. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    cancelWorkflowExecutionFailedEventAttributes -> (structure)

      

      If the event is of type ``CancelWorkflowExecutionFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``CancelWorkflowExecution`` decision for this cancellation request. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    workflowExecutionContinuedAsNewEventAttributes -> (structure)

      

      If the event is of type ``WorkflowExecutionContinuedAsNew`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      input -> (string)

        

        The input provided to the new workflow execution.

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``ContinueAsNewWorkflowExecution`` decision that started this execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      newExecutionRunId -> (string)

        

        The ``runId`` of the new workflow execution.

        

        

      executionStartToCloseTimeout -> (string)

        

        The total duration allowed for the new workflow execution.

         

        The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

        

        

      taskList -> (structure)

        

        Represents a task list.

        

        name -> (string)

          

          The name of the task list.

          

          

        

      taskPriority -> (string)

        

        

      taskStartToCloseTimeout -> (string)

        

        The maximum duration of decision tasks for the new workflow execution.

         

        The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

        

        

      childPolicy -> (string)

        

        The policy to use for the child workflow executions of the new execution if it is terminated by calling the  terminate-workflow-execution action explicitly or due to an expired timeout.

         

        The supported child policies are:

         

         
        * **TERMINATE:** the child executions will be terminated.
         
        * **REQUEST_CANCEL:** a request to cancel will be attempted for each child execution by recording a ``WorkflowExecutionCancelRequested`` event in its history. It is up to the decider to take appropriate actions when it receives an execution history with this event.
         
        * **ABANDON:** no action will be taken. The child executions will continue to run.
         

        

        

      tagList -> (list)

        

        The list of tags associated with the new workflow execution.

        

        (string)

          

          

        

      workflowType -> (structure)

        

        Represents a workflow type.

        

        name -> (string)

          

          **Required.** The name of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        version -> (string)

          

          **Required.** The version of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        

      lambdaRole -> (string)

        

        The IAM role attached to this workflow execution to use when invoking AWS Lambda functions.

        

        

      

    continueAsNewWorkflowExecutionFailedEventAttributes -> (structure)

      

      If the event is of type ``ContinueAsNewWorkflowExecutionFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``ContinueAsNewWorkflowExecution`` decision that started this execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    workflowExecutionTerminatedEventAttributes -> (structure)

      

      If the event is of type ``WorkflowExecutionTerminated`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      reason -> (string)

        

        The reason provided for the termination (if any).

        

        

      details -> (string)

        

        The details provided for the termination (if any).

        

        

      childPolicy -> (string)

        

        The policy used for the child workflow executions of this workflow execution.

         

        The supported child policies are:

         

         
        * **TERMINATE:** the child executions will be terminated.
         
        * **REQUEST_CANCEL:** a request to cancel will be attempted for each child execution by recording a ``WorkflowExecutionCancelRequested`` event in its history. It is up to the decider to take appropriate actions when it receives an execution history with this event.
         
        * **ABANDON:** no action will be taken. The child executions will continue to run.
         

        

        

      cause -> (string)

        

        If set, indicates that the workflow execution was automatically terminated, and specifies the cause. This happens if the parent workflow execution times out or is terminated and the child policy is set to terminate child executions.

        

        

      

    workflowExecutionCancelRequestedEventAttributes -> (structure)

      

      If the event is of type ``WorkflowExecutionCancelRequested`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      externalWorkflowExecution -> (structure)

        

        The external workflow execution for which the cancellation was requested.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      externalInitiatedEventId -> (long)

        

        The ID of the ``RequestCancelExternalWorkflowExecutionInitiated`` event corresponding to the ``RequestCancelExternalWorkflowExecution`` decision to cancel this workflow execution.The source event with this ID can be found in the history of the source workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      cause -> (string)

        

        If set, indicates that the request to cancel the workflow execution was automatically generated, and specifies the cause. This happens if the parent workflow execution times out or is terminated, and the child policy is set to cancel child executions.

        

        

      

    decisionTaskScheduledEventAttributes -> (structure)

      

      If the event is of type ``DecisionTaskScheduled`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      taskList -> (structure)

        

        The name of the task list in which the decision task was scheduled.

        

        name -> (string)

          

          The name of the task list.

          

          

        

      taskPriority -> (string)

        

        *Optional.* A task priority that, if set, specifies the priority for this decision task. Valid values are integers that range from Java's ``Integer.MIN_VALUE`` (-2147483648) to ``Integer.MAX_VALUE`` (2147483647). Higher numbers indicate higher priority.

         

        For more information about setting task priority, see `Setting Task Priority`_ in the *Amazon Simple Workflow Developer Guide* .

        

        

      startToCloseTimeout -> (string)

        

        The maximum duration for this decision task. The task is considered timed out if it does not completed within this duration.

         

        The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

        

        

      

    decisionTaskStartedEventAttributes -> (structure)

      

      If the event is of type ``DecisionTaskStarted`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      identity -> (string)

        

        Identity of the decider making the request. This enables diagnostic tracing when problems arise. The form of this identity is user defined.

        

        

      scheduledEventId -> (long)

        

        The ID of the ``DecisionTaskScheduled`` event that was recorded when this decision task was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    decisionTaskCompletedEventAttributes -> (structure)

      

      If the event is of type ``DecisionTaskCompleted`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      executionContext -> (string)

        

        User defined context for the workflow execution.

        

        

      scheduledEventId -> (long)

        

        The ID of the ``DecisionTaskScheduled`` event that was recorded when this decision task was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``DecisionTaskStarted`` event recorded when this decision task was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    decisionTaskTimedOutEventAttributes -> (structure)

      

      If the event is of type ``DecisionTaskTimedOut`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      timeoutType -> (string)

        

        The type of timeout that expired before the decision task could be completed.

        

        

      scheduledEventId -> (long)

        

        The ID of the ``DecisionTaskScheduled`` event that was recorded when this decision task was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``DecisionTaskStarted`` event recorded when this decision task was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    activityTaskScheduledEventAttributes -> (structure)

      

      If the event is of type ``ActivityTaskScheduled`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      activityType -> (structure)

        

        The type of the activity task.

        

        name -> (string)

          

          The name of this activity.

           

          .. note::

            The combination of activity type name and version must be unique within a domain.

          

          

        version -> (string)

          

          The version of this activity.

           

          .. note::

            The combination of activity type name and version must be unique with in a domain.

          

          

        

      activityId -> (string)

        

        The unique ID of the activity task.

        

        

      input -> (string)

        

        The input provided to the activity task.

        

        

      control -> (string)

        

        *Optional.* Data attached to the event that can be used by the decider in subsequent workflow tasks. This data is not sent to the activity.

        

        

      scheduleToStartTimeout -> (string)

        

        The maximum amount of time the activity task can wait to be assigned to a worker.

        

        

      scheduleToCloseTimeout -> (string)

        

        The maximum amount of time for this activity task.

        

        

      startToCloseTimeout -> (string)

        

        The maximum amount of time a worker may take to process the activity task.

        

        

      taskList -> (structure)

        

        The task list in which the activity task has been scheduled.

        

        name -> (string)

          

          The name of the task list.

          

          

        

      taskPriority -> (string)

        

        *Optional.* The priority to assign to the scheduled activity task. If set, this will override any default priority value that was assigned when the activity type was registered.

         

        Valid values are integers that range from Java's ``Integer.MIN_VALUE`` (-2147483648) to ``Integer.MAX_VALUE`` (2147483647). Higher numbers indicate higher priority.

         

        For more information about setting task priority, see `Setting Task Priority`_ in the *Amazon Simple Workflow Developer Guide* .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision that resulted in the scheduling of this activity task. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      heartbeatTimeout -> (string)

        

        The maximum time before which the worker processing this task must report progress by calling  record-activity-task-heartbeat . If the timeout is exceeded, the activity task is automatically timed out. If the worker subsequently attempts to record a heartbeat or return a result, it will be ignored.

        

        

      

    activityTaskStartedEventAttributes -> (structure)

      

      If the event is of type ``ActivityTaskStarted`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      identity -> (string)

        

        Identity of the worker that was assigned this task. This aids diagnostics when problems arise. The form of this identity is user defined.

        

        

      scheduledEventId -> (long)

        

        The ID of the ``ActivityTaskScheduled`` event that was recorded when this activity task was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    activityTaskCompletedEventAttributes -> (structure)

      

      If the event is of type ``ActivityTaskCompleted`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      result -> (string)

        

        The results of the activity task (if any).

        

        

      scheduledEventId -> (long)

        

        The ID of the ``ActivityTaskScheduled`` event that was recorded when this activity task was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``ActivityTaskStarted`` event recorded when this activity task was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    activityTaskFailedEventAttributes -> (structure)

      

      If the event is of type ``ActivityTaskFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      reason -> (string)

        

        The reason provided for the failure (if any).

        

        

      details -> (string)

        

        The details of the failure (if any).

        

        

      scheduledEventId -> (long)

        

        The ID of the ``ActivityTaskScheduled`` event that was recorded when this activity task was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``ActivityTaskStarted`` event recorded when this activity task was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    activityTaskTimedOutEventAttributes -> (structure)

      

      If the event is of type ``ActivityTaskTimedOut`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      timeoutType -> (string)

        

        The type of the timeout that caused this event.

        

        

      scheduledEventId -> (long)

        

        The ID of the ``ActivityTaskScheduled`` event that was recorded when this activity task was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``ActivityTaskStarted`` event recorded when this activity task was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      details -> (string)

        

        Contains the content of the ``details`` parameter for the last call made by the activity to ``record-activity-task-heartbeat`` .

        

        

      

    activityTaskCanceledEventAttributes -> (structure)

      

      If the event is of type ``ActivityTaskCanceled`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      details -> (string)

        

        Details of the cancellation (if any).

        

        

      scheduledEventId -> (long)

        

        The ID of the ``ActivityTaskScheduled`` event that was recorded when this activity task was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``ActivityTaskStarted`` event recorded when this activity task was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      latestCancelRequestedEventId -> (long)

        

        If set, contains the ID of the last ``ActivityTaskCancelRequested`` event recorded for this activity task. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    activityTaskCancelRequestedEventAttributes -> (structure)

      

      If the event is of type ``ActivityTaskcancelRequested`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``RequestCancelActivityTask`` decision for this cancellation request. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      activityId -> (string)

        

        The unique ID of the task.

        

        

      

    workflowExecutionSignaledEventAttributes -> (structure)

      

      If the event is of type ``WorkflowExecutionSignaled`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      signalName -> (string)

        

        The name of the signal received. The decider can use the signal name and inputs to determine how to the process the signal.

        

        

      input -> (string)

        

        Inputs provided with the signal (if any). The decider can use the signal name and inputs to determine how to process the signal.

        

        

      externalWorkflowExecution -> (structure)

        

        The workflow execution that sent the signal. This is set only of the signal was sent by another workflow execution.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      externalInitiatedEventId -> (long)

        

        The ID of the ``SignalExternalWorkflowExecutionInitiated`` event corresponding to the ``SignalExternalWorkflow`` decision to signal this workflow execution.The source event with this ID can be found in the history of the source workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event. This field is set only if the signal was initiated by another workflow execution.

        

        

      

    markerRecordedEventAttributes -> (structure)

      

      If the event is of type ``MarkerRecorded`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      markerName -> (string)

        

        The name of the marker.

        

        

      details -> (string)

        

        Details of the marker (if any).

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``RecordMarker`` decision that requested this marker. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    recordMarkerFailedEventAttributes -> (structure)

      

      If the event is of type ``DecisionTaskFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      markerName -> (string)

        

        The marker's name.

        

        

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``RecordMarkerFailed`` decision for this cancellation request. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    timerStartedEventAttributes -> (structure)

      

      If the event is of type ``TimerStarted`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      timerId -> (string)

        

        The unique ID of the timer that was started.

        

        

      control -> (string)

        

        *Optional.* Data attached to the event that can be used by the decider in subsequent workflow tasks.

        

        

      startToFireTimeout -> (string)

        

        The duration of time after which the timer will fire.

         

        The duration is specified in seconds; an integer greater than or equal to 0.

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``StartTimer`` decision for this activity task. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    timerFiredEventAttributes -> (structure)

      

      If the event is of type ``TimerFired`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      timerId -> (string)

        

        The unique ID of the timer that fired.

        

        

      startedEventId -> (long)

        

        The ID of the ``TimerStarted`` event that was recorded when this timer was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    timerCanceledEventAttributes -> (structure)

      

      If the event is of type ``TimerCanceled`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      timerId -> (string)

        

        The unique ID of the timer that was canceled. 

        

        

      startedEventId -> (long)

        

        The ID of the ``TimerStarted`` event that was recorded when this timer was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``CancelTimer`` decision to cancel this timer. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    startChildWorkflowExecutionInitiatedEventAttributes -> (structure)

      

      If the event is of type ``StartChildWorkflowExecutionInitiated`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowId -> (string)

        

        The ``workflowId`` of the child workflow execution.

        

        

      workflowType -> (structure)

        

        The type of the child workflow execution.

        

        name -> (string)

          

          **Required.** The name of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        version -> (string)

          

          **Required.** The version of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        

      control -> (string)

        

        *Optional.* Data attached to the event that can be used by the decider in subsequent decision tasks. This data is not sent to the activity.

        

        

      input -> (string)

        

        The inputs provided to the child workflow execution (if any).

        

        

      executionStartToCloseTimeout -> (string)

        

        The maximum duration for the child workflow execution. If the workflow execution is not closed within this duration, it will be timed out and force terminated.

         

        The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

        

        

      taskList -> (structure)

        

        The name of the task list used for the decision tasks of the child workflow execution.

        

        name -> (string)

          

          The name of the task list.

          

          

        

      taskPriority -> (string)

        

        *Optional.* The priority assigned for the decision tasks for this workflow execution. Valid values are integers that range from Java's ``Integer.MIN_VALUE`` (-2147483648) to ``Integer.MAX_VALUE`` (2147483647). Higher numbers indicate higher priority.

         

        For more information about setting task priority, see `Setting Task Priority`_ in the *Amazon Simple Workflow Developer Guide* .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``StartChildWorkflowExecution`` decision to request this child workflow execution. This information can be useful for diagnosing problems by tracing back the cause of events.

        

        

      childPolicy -> (string)

        

        The policy to use for the child workflow executions if this execution gets terminated by explicitly calling the  terminate-workflow-execution action or due to an expired timeout.

         

        The supported child policies are:

         

         
        * **TERMINATE:** the child executions will be terminated.
         
        * **REQUEST_CANCEL:** a request to cancel will be attempted for each child execution by recording a ``WorkflowExecutionCancelRequested`` event in its history. It is up to the decider to take appropriate actions when it receives an execution history with this event.
         
        * **ABANDON:** no action will be taken. The child executions will continue to run.
         

        

        

      taskStartToCloseTimeout -> (string)

        

        The maximum duration allowed for the decision tasks for this workflow execution.

         

        The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

        

        

      tagList -> (list)

        

        The list of tags to associated with the child workflow execution.

        

        (string)

          

          

        

      lambdaRole -> (string)

        

        The IAM role attached to this workflow execution to use when invoking AWS Lambda functions.

        

        

      

    childWorkflowExecutionStartedEventAttributes -> (structure)

      

      If the event is of type ``ChildWorkflowExecutionStarted`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowExecution -> (structure)

        

        The child workflow execution that was started.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      workflowType -> (structure)

        

        The type of the child workflow execution. 

        

        name -> (string)

          

          **Required.** The name of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        version -> (string)

          

          **Required.** The version of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        

      initiatedEventId -> (long)

        

        The ID of the ``StartChildWorkflowExecutionInitiated`` event corresponding to the ``StartChildWorkflowExecution`` decision to start this child workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    childWorkflowExecutionCompletedEventAttributes -> (structure)

      

      If the event is of type ``ChildWorkflowExecutionCompleted`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowExecution -> (structure)

        

        The child workflow execution that was completed.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      workflowType -> (structure)

        

        The type of the child workflow execution.

        

        name -> (string)

          

          **Required.** The name of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        version -> (string)

          

          **Required.** The version of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        

      result -> (string)

        

        The result of the child workflow execution (if any).

        

        

      initiatedEventId -> (long)

        

        The ID of the ``StartChildWorkflowExecutionInitiated`` event corresponding to the ``StartChildWorkflowExecution`` decision to start this child workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``ChildWorkflowExecutionStarted`` event recorded when this child workflow execution was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    childWorkflowExecutionFailedEventAttributes -> (structure)

      

      If the event is of type ``ChildWorkflowExecutionFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowExecution -> (structure)

        

        The child workflow execution that failed.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      workflowType -> (structure)

        

        The type of the child workflow execution.

        

        name -> (string)

          

          **Required.** The name of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        version -> (string)

          

          **Required.** The version of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        

      reason -> (string)

        

        The reason for the failure (if provided).

        

        

      details -> (string)

        

        The details of the failure (if provided).

        

        

      initiatedEventId -> (long)

        

        The ID of the ``StartChildWorkflowExecutionInitiated`` event corresponding to the ``StartChildWorkflowExecution`` decision to start this child workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``ChildWorkflowExecutionStarted`` event recorded when this child workflow execution was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    childWorkflowExecutionTimedOutEventAttributes -> (structure)

      

      If the event is of type ``ChildWorkflowExecutionTimedOut`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowExecution -> (structure)

        

        The child workflow execution that timed out.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      workflowType -> (structure)

        

        The type of the child workflow execution.

        

        name -> (string)

          

          **Required.** The name of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        version -> (string)

          

          **Required.** The version of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        

      timeoutType -> (string)

        

        The type of the timeout that caused the child workflow execution to time out.

        

        

      initiatedEventId -> (long)

        

        The ID of the ``StartChildWorkflowExecutionInitiated`` event corresponding to the ``StartChildWorkflowExecution`` decision to start this child workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``ChildWorkflowExecutionStarted`` event recorded when this child workflow execution was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    childWorkflowExecutionCanceledEventAttributes -> (structure)

      

      If the event is of type ``ChildWorkflowExecutionCanceled`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowExecution -> (structure)

        

        The child workflow execution that was canceled.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      workflowType -> (structure)

        

        The type of the child workflow execution.

        

        name -> (string)

          

          **Required.** The name of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        version -> (string)

          

          **Required.** The version of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        

      details -> (string)

        

        Details of the cancellation (if provided).

        

        

      initiatedEventId -> (long)

        

        The ID of the ``StartChildWorkflowExecutionInitiated`` event corresponding to the ``StartChildWorkflowExecution`` decision to start this child workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``ChildWorkflowExecutionStarted`` event recorded when this child workflow execution was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    childWorkflowExecutionTerminatedEventAttributes -> (structure)

      

      If the event is of type ``ChildWorkflowExecutionTerminated`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowExecution -> (structure)

        

        The child workflow execution that was terminated.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      workflowType -> (structure)

        

        The type of the child workflow execution.

        

        name -> (string)

          

          **Required.** The name of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        version -> (string)

          

          **Required.** The version of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        

      initiatedEventId -> (long)

        

        The ID of the ``StartChildWorkflowExecutionInitiated`` event corresponding to the ``StartChildWorkflowExecution`` decision to start this child workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``ChildWorkflowExecutionStarted`` event recorded when this child workflow execution was started. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    signalExternalWorkflowExecutionInitiatedEventAttributes -> (structure)

      

      If the event is of type ``SignalExternalWorkflowExecutionInitiated`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowId -> (string)

        

        The ``workflowId`` of the external workflow execution.

        

        

      runId -> (string)

        

        The ``runId`` of the external workflow execution to send the signal to.

        

        

      signalName -> (string)

        

        The name of the signal.

        

        

      input -> (string)

        

        Input provided to the signal (if any).

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``SignalExternalWorkflowExecution`` decision for this signal. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      control -> (string)

        

        *Optional.* data attached to the event that can be used by the decider in subsequent decision tasks.

        

        

      

    externalWorkflowExecutionSignaledEventAttributes -> (structure)

      

      If the event is of type ``ExternalWorkflowExecutionSignaled`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowExecution -> (structure)

        

        The external workflow execution that the signal was delivered to.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      initiatedEventId -> (long)

        

        The ID of the ``SignalExternalWorkflowExecutionInitiated`` event corresponding to the ``SignalExternalWorkflowExecution`` decision to request this signal. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    signalExternalWorkflowExecutionFailedEventAttributes -> (structure)

      

      If the event is of type ``SignalExternalWorkflowExecutionFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowId -> (string)

        

        The ``workflowId`` of the external workflow execution that the signal was being delivered to.

        

        

      runId -> (string)

        

        The ``runId`` of the external workflow execution that the signal was being delivered to.

        

        

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      initiatedEventId -> (long)

        

        The ID of the ``SignalExternalWorkflowExecutionInitiated`` event corresponding to the ``SignalExternalWorkflowExecution`` decision to request this signal. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``SignalExternalWorkflowExecution`` decision for this signal. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      control -> (string)

        

        

      

    externalWorkflowExecutionCancelRequestedEventAttributes -> (structure)

      

      If the event is of type ``ExternalWorkflowExecutionCancelRequested`` then this member is set and provides detailed information about the event. It is not set for other event types. 

      

      workflowExecution -> (structure)

        

        The external workflow execution to which the cancellation request was delivered.

        

        workflowId -> (string)

          

          The user defined identifier associated with the workflow execution.

          

          

        runId -> (string)

          

          A system-generated unique identifier for the workflow execution.

          

          

        

      initiatedEventId -> (long)

        

        The ID of the ``RequestCancelExternalWorkflowExecutionInitiated`` event corresponding to the ``RequestCancelExternalWorkflowExecution`` decision to cancel this external workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    requestCancelExternalWorkflowExecutionInitiatedEventAttributes -> (structure)

      

      If the event is of type ``RequestCancelExternalWorkflowExecutionInitiated`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowId -> (string)

        

        The ``workflowId`` of the external workflow execution to be canceled.

        

        

      runId -> (string)

        

        The ``runId`` of the external workflow execution to be canceled.

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``RequestCancelExternalWorkflowExecution`` decision for this cancellation request. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      control -> (string)

        

        *Optional.* Data attached to the event that can be used by the decider in subsequent workflow tasks.

        

        

      

    requestCancelExternalWorkflowExecutionFailedEventAttributes -> (structure)

      

      If the event is of type ``RequestCancelExternalWorkflowExecutionFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowId -> (string)

        

        The ``workflowId`` of the external workflow to which the cancel request was to be delivered.

        

        

      runId -> (string)

        

        The ``runId`` of the external workflow execution.

        

        

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      initiatedEventId -> (long)

        

        The ID of the ``RequestCancelExternalWorkflowExecutionInitiated`` event corresponding to the ``RequestCancelExternalWorkflowExecution`` decision to cancel this external workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``RequestCancelExternalWorkflowExecution`` decision for this cancellation request. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      control -> (string)

        

        

      

    scheduleActivityTaskFailedEventAttributes -> (structure)

      

      If the event is of type ``ScheduleActivityTaskFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      activityType -> (structure)

        

        The activity type provided in the ``ScheduleActivityTask`` decision that failed.

        

        name -> (string)

          

          The name of this activity.

           

          .. note::

            The combination of activity type name and version must be unique within a domain.

          

          

        version -> (string)

          

          The version of this activity.

           

          .. note::

            The combination of activity type name and version must be unique with in a domain.

          

          

        

      activityId -> (string)

        

        The activityId provided in the ``ScheduleActivityTask`` decision that failed.

        

        

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision that resulted in the scheduling of this activity task. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    requestCancelActivityTaskFailedEventAttributes -> (structure)

      

      If the event is of type ``RequestCancelActivityTaskFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      activityId -> (string)

        

        The activityId provided in the ``RequestCancelActivityTask`` decision that failed.

        

        

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``RequestCancelActivityTask`` decision for this cancellation request. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    startTimerFailedEventAttributes -> (structure)

      

      If the event is of type ``StartTimerFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      timerId -> (string)

        

        The timerId provided in the ``StartTimer`` decision that failed.

        

        

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``StartTimer`` decision for this activity task. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    cancelTimerFailedEventAttributes -> (structure)

      

      If the event is of type ``CancelTimerFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      timerId -> (string)

        

        The timerId provided in the ``CancelTimer`` decision that failed.

        

        

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``CancelTimer`` decision to cancel this timer. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    startChildWorkflowExecutionFailedEventAttributes -> (structure)

      

      If the event is of type ``StartChildWorkflowExecutionFailed`` then this member is set and provides detailed information about the event. It is not set for other event types.

      

      workflowType -> (structure)

        

        The workflow type provided in the ``StartChildWorkflowExecution`` decision that failed.

        

        name -> (string)

          

          **Required.** The name of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        version -> (string)

          

          **Required.** The version of the workflow type.

           

          .. note::

            The combination of workflow type name and version must be unique with in a domain.

          

          

        

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      workflowId -> (string)

        

        The ``workflowId`` of the child workflow execution.

        

        

      initiatedEventId -> (long)

        

        The ID of the ``StartChildWorkflowExecutionInitiated`` event corresponding to the ``StartChildWorkflowExecution`` decision to start this child workflow execution. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision task that resulted in the ``StartChildWorkflowExecution`` decision to request this child workflow execution. This information can be useful for diagnosing problems by tracing back the cause of events.

        

        

      control -> (string)

        

        

      

    lambdaFunctionScheduledEventAttributes -> (structure)

      

      Provides details for the ``LambdaFunctionScheduled`` event.

      

      id -> (string)

        

        The unique Amazon SWF ID for the AWS Lambda task.

        

        

      name -> (string)

        

        The name of the scheduled AWS Lambda function.

        

        

      input -> (string)

        

        Input provided to the AWS Lambda function.

        

        

      startToCloseTimeout -> (string)

        

        The maximum time, in seconds, that the AWS Lambda function can take to execute from start to close before it is marked as failed.

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event for the decision that resulted in the scheduling of this AWS Lambda function. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    lambdaFunctionStartedEventAttributes -> (structure)

      

      Provides details for the ``LambdaFunctionStarted`` event.

      

      scheduledEventId -> (long)

        

        The ID of the ``LambdaFunctionScheduled`` event that was recorded when this AWS Lambda function was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    lambdaFunctionCompletedEventAttributes -> (structure)

      

      Provides details for the ``LambdaFunctionCompleted`` event.

      

      scheduledEventId -> (long)

        

        The ID of the ``LambdaFunctionScheduled`` event that was recorded when this AWS Lambda function was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``LambdaFunctionStarted`` event recorded in the history.

        

        

      result -> (string)

        

        The result of the function execution (if any).

        

        

      

    lambdaFunctionFailedEventAttributes -> (structure)

      

      Provides details for the ``LambdaFunctionFailed`` event.

      

      scheduledEventId -> (long)

        

        The ID of the ``LambdaFunctionScheduled`` event that was recorded when this AWS Lambda function was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``LambdaFunctionStarted`` event recorded in the history.

        

        

      reason -> (string)

        

        The reason provided for the failure (if any).

        

        

      details -> (string)

        

        The details of the failure (if any).

        

        

      

    lambdaFunctionTimedOutEventAttributes -> (structure)

      

      Provides details for the ``LambdaFunctionTimedOut`` event.

      

      scheduledEventId -> (long)

        

        The ID of the ``LambdaFunctionScheduled`` event that was recorded when this AWS Lambda function was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      startedEventId -> (long)

        

        The ID of the ``LambdaFunctionStarted`` event recorded in the history.

        

        

      timeoutType -> (string)

        

        The type of the timeout that caused this event.

        

        

      

    scheduleLambdaFunctionFailedEventAttributes -> (structure)

      

      Provides details for the ``ScheduleLambdaFunctionFailed`` event.

      

      id -> (string)

        

        The unique Amazon SWF ID of the AWS Lambda task.

        

        

      name -> (string)

        

        The name of the scheduled AWS Lambda function.

        

        

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      decisionTaskCompletedEventId -> (long)

        

        The ID of the ``DecisionTaskCompleted`` event corresponding to the decision that resulted in the scheduling of this AWS Lambda function. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      

    startLambdaFunctionFailedEventAttributes -> (structure)

      

      Provides details for the ``StartLambdaFunctionFailed`` event.

      

      scheduledEventId -> (long)

        

        The ID of the ``LambdaFunctionScheduled`` event that was recorded when this AWS Lambda function was scheduled. This information can be useful for diagnosing problems by tracing back the chain of events leading up to this event.

        

        

      cause -> (string)

        

        The cause of the failure. This information is generated by the system and can be useful for diagnostic purposes.

         

        .. note::

          If **cause** is set to OPERATION_NOT_PERMITTED, the decision failed because it lacked sufficient permissions. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .

        

        

      message -> (string)

        

        The error message (if any).

        

        

      

    

  

nextPageToken -> (string)

  

  If a ``NextPageToken`` was returned by a previous call, there are more results available. To retrieve the next page of results, make the call again using the returned token in ``nextPageToken`` . Keep all other arguments unchanged.

   

  The configured ``maximumPageSize`` determines how many results can be returned in a single call.

  

  



.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
.. _Setting Task Priority: http://docs.aws.amazon.com/amazonswf/latest/developerguide/programming-priority.html
