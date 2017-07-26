[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf describe-workflow-type:


**********************
describe-workflow-type
**********************



===========
Description
===========



Returns information about the specified *workflow type* . This includes configuration settings specified when the type was registered and other information such as creation date, current status, and so on.

 

**Access Control** 

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains.
 
* Use an ``Action`` element to allow or deny permission to call this action.
 
* Constrain the following parameters by using a ``Condition`` element with the appropriate keys. 

   
  * ``workflowType.name`` : String constraint. The key is ``swf:workflowType.name`` .
   
  * ``workflowType.version`` : String constraint. The key is ``swf:workflowType.version`` .
   

 
 

 

If the caller does not have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's **cause** parameter will be set to OPERATION_NOT_PERMITTED. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .



========
Synopsis
========

::

    describe-workflow-type
  --domain <value>
  --workflow-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain in which this workflow type is registered.

  

``--workflow-type`` (structure)


  The workflow type to describe.

  



Shorthand Syntax::

    name=string,version=string




JSON Syntax::

  {
    "name": "string",
    "version": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

typeInfo -> (structure)

  

  General information about the workflow type.

   

  The status of the workflow type (returned in the WorkflowTypeInfo structure) can be one of the following.

   

   
  * **REGISTERED** : The type is registered and available. Workers supporting this type should be running.
   
  * **DEPRECATED** : The type was deprecated using  deprecate-workflow-type , but is still in use. You should keep workers supporting this type running. You cannot create new workflow executions of this type.
   

  

  workflowType -> (structure)

    

    The workflow type this information is about.

    

    name -> (string)

      

      **Required.** The name of the workflow type.

       

      .. note::

        The combination of workflow type name and version must be unique with in a domain.

      

      

    version -> (string)

      

      **Required.** The version of the workflow type.

       

      .. note::

        The combination of workflow type name and version must be unique with in a domain.

      

      

    

  status -> (string)

    

    The current status of the workflow type.

    

    

  description -> (string)

    

    The description of the type registered through  register-workflow-type .

    

    

  creationDate -> (timestamp)

    

    The date when this type was registered.

    

    

  deprecationDate -> (timestamp)

    

    If the type is in deprecated state, then it is set to the date when the type was deprecated.

    

    

  

configuration -> (structure)

  

  Configuration settings of the workflow type registered through  register-workflow-type 

  

  defaultTaskStartToCloseTimeout -> (string)

    

    *Optional.* The default maximum duration, specified when registering the workflow type, that a decision task for executions of this workflow type might take before returning completion or failure. If the task does not close in the specified time then the task is automatically timed out and rescheduled. If the decider eventually reports a completion or failure, it is ignored. This default can be overridden when starting a workflow execution using the  start-workflow-execution action or the ``StartChildWorkflowExecution`` decision.

     

    The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

    

    

  defaultExecutionStartToCloseTimeout -> (string)

    

    *Optional.* The default maximum duration, specified when registering the workflow type, for executions of this workflow type. This default can be overridden when starting a workflow execution using the  start-workflow-execution action or the ``StartChildWorkflowExecution`` decision.

     

    The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

    

    

  defaultTaskList -> (structure)

    

    *Optional.* The default task list, specified when registering the workflow type, for decisions tasks scheduled for workflow executions of this type. This default can be overridden when starting a workflow execution using the  start-workflow-execution action or the ``StartChildWorkflowExecution`` decision.

    

    name -> (string)

      

      The name of the task list.

      

      

    

  defaultTaskPriority -> (string)

    

    *Optional.* The default task priority, specified when registering the workflow type, for all decision tasks of this workflow type. This default can be overridden when starting a workflow execution using the  start-workflow-execution action or the ``StartChildWorkflowExecution`` decision.

     

    Valid values are integers that range from Java's ``Integer.MIN_VALUE`` (-2147483648) to ``Integer.MAX_VALUE`` (2147483647). Higher numbers indicate higher priority.

     

    For more information about setting task priority, see `Setting Task Priority`_ in the *Amazon Simple Workflow Developer Guide* .

    

    

  defaultChildPolicy -> (string)

    

    *Optional.* The default policy to use for the child workflow executions when a workflow execution of this type is terminated, by calling the  terminate-workflow-execution action explicitly or due to an expired timeout. This default can be overridden when starting a workflow execution using the  start-workflow-execution action or the ``StartChildWorkflowExecution`` decision.

     

    The supported child policies are:

     

     
    * **TERMINATE:** the child executions will be terminated.
     
    * **REQUEST_CANCEL:** a request to cancel will be attempted for each child execution by recording a ``WorkflowExecutionCancelRequested`` event in its history. It is up to the decider to take appropriate actions when it receives an execution history with this event.
     
    * **ABANDON:** no action will be taken. The child executions will continue to run.
     

    

    

  defaultLambdaRole -> (string)

    

    The default IAM role to use when a workflow execution invokes a AWS Lambda function.

    

    

  



.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
.. _Setting Task Priority: http://docs.aws.amazon.com/amazonswf/latest/developerguide/programming-priority.html
