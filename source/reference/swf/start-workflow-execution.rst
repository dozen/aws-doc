[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf start-workflow-execution:


************************
start-workflow-execution
************************



===========
Description
===========



Starts an execution of the workflow type in the specified domain using the provided ``workflowId`` and input data.

 

This action returns the newly started workflow execution.

 

**Access Control** 

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains.
 
* Use an ``Action`` element to allow or deny permission to call this action.
 
* Constrain the following parameters by using a ``Condition`` element with the appropriate keys. 

   
  * ``tagList.member.0`` : The key is ``swf:tagList.member.0`` .
   
  * ``tagList.member.1`` : The key is ``swf:tagList.member.1`` .
   
  * ``tagList.member.2`` : The key is ``swf:tagList.member.2`` .
   
  * ``tagList.member.3`` : The key is ``swf:tagList.member.3`` .
   
  * ``tagList.member.4`` : The key is ``swf:tagList.member.4`` .
   
  * ``taskList`` : String constraint. The key is ``swf:taskList.name`` .
   
  * ``workflowType.name`` : String constraint. The key is ``swf:workflowType.name`` .
   
  * ``workflowType.version`` : String constraint. The key is ``swf:workflowType.version`` .
   

 
 

 

If the caller does not have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's **cause** parameter will be set to OPERATION_NOT_PERMITTED. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .



========
Synopsis
========

::

    start-workflow-execution
  --domain <value>
  --workflow-id <value>
  --workflow-type <value>
  [--task-list <value>]
  [--task-priority <value>]
  [--input <value>]
  [--execution-start-to-close-timeout <value>]
  [--tag-list <value>]
  [--task-start-to-close-timeout <value>]
  [--child-policy <value>]
  [--lambda-role <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain in which the workflow execution is created.

  

``--workflow-id`` (string)


  The user defined identifier associated with the workflow execution. You can use this to associate a custom identifier with the workflow execution. You may specify the same identifier if a workflow execution is logically a *restart* of a previous execution. You cannot have two open workflow executions with the same ``workflowId`` at the same time.

   

  The specified string must not start or end with whitespace. It must not contain a ``:`` (colon), ``/`` (slash), ``|`` (vertical bar), or any control characters (\u0000-\u001f | \u007f - \u009f). Also, it must not contain the literal string quotarnquot.

  

``--workflow-type`` (structure)


  The type of the workflow to start.

  



Shorthand Syntax::

    name=string,version=string




JSON Syntax::

  {
    "name": "string",
    "version": "string"
  }



``--task-list`` (structure)


  The task list to use for the decision tasks generated for this workflow execution. This overrides the ``defaultTaskList`` specified when registering the workflow type.

   

  .. note::

    A task list for this workflow execution must be specified either as a default for the workflow type or through this parameter. If neither this parameter is set nor a default task list was specified at registration time then a fault will be returned.

   

  The specified string must not start or end with whitespace. It must not contain a ``:`` (colon), ``/`` (slash), ``|`` (vertical bar), or any control characters (\u0000-\u001f | \u007f - \u009f). Also, it must not contain the literal string quotarnquot.

  



Shorthand Syntax::

    name=string




JSON Syntax::

  {
    "name": "string"
  }



``--task-priority`` (string)


  The task priority to use for this workflow execution. This will override any default priority that was assigned when the workflow type was registered. If not set, then the default task priority for the workflow type will be used. Valid values are integers that range from Java's ``Integer.MIN_VALUE`` (-2147483648) to ``Integer.MAX_VALUE`` (2147483647). Higher numbers indicate higher priority.

   

  For more information about setting task priority, see `Setting Task Priority`_ in the *Amazon Simple Workflow Developer Guide* .

  

``--input`` (string)


  The input for the workflow execution. This is a free form string which should be meaningful to the workflow you are starting. This ``input`` is made available to the new workflow execution in the ``WorkflowExecutionStarted`` history event.

  

``--execution-start-to-close-timeout`` (string)


  The total duration for this workflow execution. This overrides the defaultExecutionStartToCloseTimeout specified when registering the workflow type.

   

  The duration is specified in seconds; an integer greater than or equal to 0. Exceeding this limit will cause the workflow execution to time out. Unlike some of the other timeout parameters in Amazon SWF, you cannot specify a value of "NONE" for this timeout; there is a one-year max limit on the time that a workflow execution can run.

   

  .. note::

    An execution start-to-close timeout must be specified either through this parameter or as a default when the workflow type is registered. If neither this parameter nor a default execution start-to-close timeout is specified, a fault is returned.

  

``--tag-list`` (list)


  The list of tags to associate with the workflow execution. You can specify a maximum of 5 tags. You can list workflow executions with a specific tag by calling  list-open-workflow-executions or  list-closed-workflow-executions and specifying a  TagFilter .

  



Syntax::

  "string" "string" ...



``--task-start-to-close-timeout`` (string)


  Specifies the maximum duration of decision tasks for this workflow execution. This parameter overrides the ``defaultTaskStartToCloseTimout`` specified when registering the workflow type using  register-workflow-type .

   

  The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

   

  .. note::

    A task start-to-close timeout for this workflow execution must be specified either as a default for the workflow type or through this parameter. If neither this parameter is set nor a default task start-to-close timeout was specified at registration time then a fault will be returned.

  

``--child-policy`` (string)


  If set, specifies the policy to use for the child workflow executions of this workflow execution if it is terminated, by calling the  terminate-workflow-execution action explicitly or due to an expired timeout. This policy overrides the default child policy specified when registering the workflow type using  register-workflow-type .

   

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

  

  

``--lambda-role`` (string)


  The ARN of an IAM role that authorizes Amazon SWF to invoke AWS Lambda functions.

   

  .. note::

    In order for this workflow execution to invoke AWS Lambda functions, an appropriate IAM role must be specified either as a default for the workflow type or through this field.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

runId -> (string)

  

  The ``runId`` of a workflow execution. This ID is generated by the service and can be used to uniquely identify the workflow execution within a domain.

  

  



.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
.. _Setting Task Priority: http://docs.aws.amazon.com/amazonswf/latest/developerguide/programming-priority.html
