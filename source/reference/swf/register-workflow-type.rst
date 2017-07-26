[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf register-workflow-type:


**********************
register-workflow-type
**********************



===========
Description
===========



Registers a new *workflow type* and its configuration settings in the specified domain.

 

The retention period for the workflow history is set by the  register-domain action.

 

.. warning::

  If the type already exists, then a ``TypeAlreadyExists`` fault is returned. You cannot change the configuration settings of a workflow type once it is registered and it must be registered as a new version.

 

**Access Control** 

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains.
 
* Use an ``Action`` element to allow or deny permission to call this action.
 
* Constrain the following parameters by using a ``Condition`` element with the appropriate keys. 

   
  * ``defaultTaskList.name`` : String constraint. The key is ``swf:defaultTaskList.name`` .
   
  * ``name`` : String constraint. The key is ``swf:name`` .
   
  * ``version`` : String constraint. The key is ``swf:version`` .
   

 
 

 

If the caller does not have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's **cause** parameter will be set to OPERATION_NOT_PERMITTED. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .



========
Synopsis
========

::

    register-workflow-type
  --domain <value>
  --name <value>
  [--description <value>]
  [--default-task-start-to-close-timeout <value>]
  [--default-execution-start-to-close-timeout <value>]
  [--default-task-list <value>]
  [--default-task-priority <value>]
  [--default-child-policy <value>]
  [--default-lambda-role <value>]
  --workflow-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain in which to register the workflow type.

  

``--name`` (string)


  The name of the workflow type.

   

  The specified string must not start or end with whitespace. It must not contain a ``:`` (colon), ``/`` (slash), ``|`` (vertical bar), or any control characters (\u0000-\u001f | \u007f - \u009f). Also, it must not contain the literal string quotarnquot.

  

``--description`` (string)


  Textual description of the workflow type.

  

``--default-task-start-to-close-timeout`` (string)


  If set, specifies the default maximum duration of decision tasks for this workflow type. This default can be overridden when starting a workflow execution using the  start-workflow-execution action or the ``StartChildWorkflowExecution`` decision.

   

  The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

  

``--default-execution-start-to-close-timeout`` (string)


  If set, specifies the default maximum duration for executions of this workflow type. You can override this default when starting an execution through the  start-workflow-execution action or ``StartChildWorkflowExecution`` decision.

   

  The duration is specified in seconds; an integer greater than or equal to 0. Unlike some of the other timeout parameters in Amazon SWF, you cannot specify a value of "NONE" for ``defaultExecutionStartToCloseTimeout`` ; there is a one-year max limit on the time that a workflow execution can run. Exceeding this limit will always cause the workflow execution to time out.

  

``--default-task-list`` (structure)


  If set, specifies the default task list to use for scheduling decision tasks for executions of this workflow type. This default is used only if a task list is not provided when starting the execution through the  start-workflow-execution action or ``StartChildWorkflowExecution`` decision.

  



Shorthand Syntax::

    name=string




JSON Syntax::

  {
    "name": "string"
  }



``--default-task-priority`` (string)


  The default task priority to assign to the workflow type. If not assigned, then "0" will be used. Valid values are integers that range from Java's ``Integer.MIN_VALUE`` (-2147483648) to ``Integer.MAX_VALUE`` (2147483647). Higher numbers indicate higher priority.

   

  For more information about setting task priority, see `Setting Task Priority`_ in the *Amazon Simple Workflow Developer Guide* .

  

``--default-child-policy`` (string)


  If set, specifies the default policy to use for the child workflow executions when a workflow execution of this type is terminated, by calling the  terminate-workflow-execution action explicitly or due to an expired timeout. This default can be overridden when starting a workflow execution using the  start-workflow-execution action or the ``StartChildWorkflowExecution`` decision.

   

  The supported child policies are:

   

   
  * **TERMINATE:** the child executions will be terminated.
   
  * **REQUEST_CANCEL:** a request to cancel will be attempted for each child execution by recording a ``WorkflowExecutionCancelRequested`` event in its history. It is up to the decider to take appropriate actions when it receives an execution history with this event.
   
  * **ABANDON:** no action will be taken. The child executions will continue to run.
   

  

  Possible values:

  
  *   ``TERMINATE``

  
  *   ``REQUEST_CANCEL``

  
  *   ``ABANDON``

  

  

``--default-lambda-role`` (string)


  The ARN of the default IAM role to use when a workflow execution of this type invokes AWS Lambda functions.

   

  This default can be overridden when starting a workflow execution using the  start-workflow-execution action or the ``StartChildWorkflowExecution`` and ``ContinueAsNewWorkflowExecution`` decision.

  

``--workflow-version`` (string)


  The version of the workflow type.

   

  .. note::

    The workflow type consists of the name and version, the combination of which must be unique within the domain. To get a list of all currently registered workflow types, use the  list-workflow-types action.

   

  The specified string must not start or end with whitespace. It must not contain a ``:`` (colon), ``/`` (slash), ``|`` (vertical bar), or any control characters (\u0000-\u001f | \u007f - \u009f). Also, it must not contain the literal string quotarnquot.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Registering a Workflow Type
---------------------------

To register a Workflow type with the AWS CLI, use the ``swf register-workflow-type`` command::

  aws swf register-workflow-type --domain DataFrobtzz --name "MySimpleWorkflow" --workflow-version "v1"

If successful, the command returns no result. On an error (for example, if you try to register the same workflow type
twice, or specify a domain that doesn't exist) you will get a response in JSON::

  {
      "message": "WorkflowType=[name=MySimpleWorkflow, version=v1]",
      "__type": "com.amazonaws.swf.base.model#TypeAlreadyExistsFault"
  }

The ``--domain``, ``--name`` and ``--workflow-version`` are required. You can also set the workflow description,
timeouts, and child workflow policy.

See Also
--------

- `RegisterWorkflowType <http://docs.aws.amazon.com/amazonswf/latest/apireference/API_RegisterWorkflowType.html>` in the
   *Amazon Simple Workflow Service API Reference*



======
Output
======

None

.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
.. _Setting Task Priority: http://docs.aws.amazon.com/amazonswf/latest/developerguide/programming-priority.html
