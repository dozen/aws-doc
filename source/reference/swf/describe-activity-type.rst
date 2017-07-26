[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf describe-activity-type:


**********************
describe-activity-type
**********************



===========
Description
===========



Returns information about the specified activity type. This includes configuration settings provided when the type was registered and other general information about the type.

 

**Access Control** 

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains.
 
* Use an ``Action`` element to allow or deny permission to call this action.
 
* Constrain the following parameters by using a ``Condition`` element with the appropriate keys. 

   
  * ``activityType.name`` : String constraint. The key is ``swf:activityType.name`` .
   
  * ``activityType.version`` : String constraint. The key is ``swf:activityType.version`` .
   

 
 

 

If the caller does not have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's **cause** parameter will be set to OPERATION_NOT_PERMITTED. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .



========
Synopsis
========

::

    describe-activity-type
  --domain <value>
  --activity-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain in which the activity type is registered.

  

``--activity-type`` (structure)


  The activity type to get information about. Activity types are identified by the ``name`` and ``version`` that were supplied when the activity was registered.

  



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

  

  General information about the activity type.

   

  The status of activity type (returned in the ActivityTypeInfo structure) can be one of the following.

   

   
  * **REGISTERED** : The type is registered and available. Workers supporting this type should be running. 
   
  * **DEPRECATED** : The type was deprecated using  deprecate-activity-type , but is still in use. You should keep workers supporting this type running. You cannot create new tasks of this type. 
   

  

  activityType -> (structure)

    

    The  activity-type type structure representing the activity type.

    

    name -> (string)

      

      The name of this activity.

       

      .. note::

        The combination of activity type name and version must be unique within a domain.

      

      

    version -> (string)

      

      The version of this activity.

       

      .. note::

        The combination of activity type name and version must be unique with in a domain.

      

      

    

  status -> (string)

    

    The current status of the activity type.

    

    

  description -> (string)

    

    The description of the activity type provided in  register-activity-type .

    

    

  creationDate -> (timestamp)

    

    The date and time this activity type was created through  register-activity-type .

    

    

  deprecationDate -> (timestamp)

    

    If DEPRECATED, the date and time  deprecate-activity-type was called.

    

    

  

configuration -> (structure)

  

  The configuration settings registered with the activity type.

  

  defaultTaskStartToCloseTimeout -> (string)

    

    *Optional.* The default maximum duration for tasks of an activity type specified when registering the activity type. You can override this default when scheduling a task through the ``ScheduleActivityTask`` decision.

     

    The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

    

    

  defaultTaskHeartbeatTimeout -> (string)

    

    *Optional.* The default maximum time, in seconds, before which a worker processing a task must report progress by calling  record-activity-task-heartbeat .

     

    You can specify this value only when *registering* an activity type. The registered default value can be overridden when you schedule a task through the ``ScheduleActivityTask`` decision. If the activity worker subsequently attempts to record a heartbeat or returns a result, the activity worker receives an ``UnknownResource`` fault. In this case, Amazon SWF no longer considers the activity task to be valid; the activity worker should clean up the activity task.

     

    The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

    

    

  defaultTaskList -> (structure)

    

    *Optional.* The default task list specified for this activity type at registration. This default is used if a task list is not provided when a task is scheduled through the ``ScheduleActivityTask`` decision. You can override the default registered task list when scheduling a task through the ``ScheduleActivityTask`` decision.

    

    name -> (string)

      

      The name of the task list.

      

      

    

  defaultTaskPriority -> (string)

    

    *Optional.* The default task priority for tasks of this activity type, specified at registration. If not set, then "0" will be used as the default priority. This default can be overridden when scheduling an activity task.

     

    Valid values are integers that range from Java's ``Integer.MIN_VALUE`` (-2147483648) to ``Integer.MAX_VALUE`` (2147483647). Higher numbers indicate higher priority.

     

    For more information about setting task priority, see `Setting Task Priority`_ in the *Amazon Simple Workflow Developer Guide* .

    

    

  defaultTaskScheduleToStartTimeout -> (string)

    

    *Optional.* The default maximum duration, specified when registering the activity type, that a task of an activity type can wait before being assigned to a worker. You can override this default when scheduling a task through the ``ScheduleActivityTask`` decision.

     

    The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

    

    

  defaultTaskScheduleToCloseTimeout -> (string)

    

    *Optional.* The default maximum duration, specified when registering the activity type, for tasks of this activity type. You can override this default when scheduling a task through the ``ScheduleActivityTask`` decision.

     

    The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

    

    

  



.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
.. _Setting Task Priority: http://docs.aws.amazon.com/amazonswf/latest/developerguide/programming-priority.html
