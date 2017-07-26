[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf register-activity-type:


**********************
register-activity-type
**********************



===========
Description
===========



Registers a new *activity type* along with its configuration settings in the specified domain.

 

.. warning::

  A ``TypeAlreadyExists`` fault is returned if the type already exists in the domain. You cannot change any configuration settings of the type after its registration, and it must be registered as a new version.

 

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

    register-activity-type
  --domain <value>
  --name <value>
  [--description <value>]
  [--default-task-start-to-close-timeout <value>]
  [--default-task-heartbeat-timeout <value>]
  [--default-task-list <value>]
  [--default-task-priority <value>]
  [--default-task-schedule-to-start-timeout <value>]
  [--default-task-schedule-to-close-timeout <value>]
  --activity-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain in which this activity is to be registered.

  

``--name`` (string)


  The name of the activity type within the domain.

   

  The specified string must not start or end with whitespace. It must not contain a ``:`` (colon), ``/`` (slash), ``|`` (vertical bar), or any control characters (\u0000-\u001f | \u007f - \u009f). Also, it must not contain the literal string quotarnquot.

  

``--description`` (string)


  A textual description of the activity type.

  

``--default-task-start-to-close-timeout`` (string)


  If set, specifies the default maximum duration that a worker can take to process tasks of this activity type. This default can be overridden when scheduling an activity task using the ``ScheduleActivityTask`` decision.

   

  The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

  

``--default-task-heartbeat-timeout`` (string)


  If set, specifies the default maximum time before which a worker processing a task of this type must report progress by calling  record-activity-task-heartbeat . If the timeout is exceeded, the activity task is automatically timed out. This default can be overridden when scheduling an activity task using the ``ScheduleActivityTask`` decision. If the activity worker subsequently attempts to record a heartbeat or returns a result, the activity worker receives an ``UnknownResource`` fault. In this case, Amazon SWF no longer considers the activity task to be valid; the activity worker should clean up the activity task.

   

  The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

  

``--default-task-list`` (structure)


  If set, specifies the default task list to use for scheduling tasks of this activity type. This default task list is used if a task list is not provided when a task is scheduled through the ``ScheduleActivityTask`` decision.

  



Shorthand Syntax::

    name=string




JSON Syntax::

  {
    "name": "string"
  }



``--default-task-priority`` (string)


  The default task priority to assign to the activity type. If not assigned, then "0" will be used. Valid values are integers that range from Java's ``Integer.MIN_VALUE`` (-2147483648) to ``Integer.MAX_VALUE`` (2147483647). Higher numbers indicate higher priority.

   

  For more information about setting task priority, see `Setting Task Priority`_ in the *Amazon Simple Workflow Developer Guide* .

  

``--default-task-schedule-to-start-timeout`` (string)


  If set, specifies the default maximum duration that a task of this activity type can wait before being assigned to a worker. This default can be overridden when scheduling an activity task using the ``ScheduleActivityTask`` decision.

   

  The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

  

``--default-task-schedule-to-close-timeout`` (string)


  If set, specifies the default maximum duration for a task of this activity type. This default can be overridden when scheduling an activity task using the ``ScheduleActivityTask`` decision.

   

  The duration is specified in seconds; an integer greater than or equal to 0. The value "NONE" can be used to specify unlimited duration.

  

``--activity-version`` (string)


  The version of the activity type.

   

  .. note::

    The activity type consists of the name and version, the combination of which must be unique within the domain.

   

  The specified string must not start or end with whitespace. It must not contain a ``:`` (colon), ``/`` (slash), ``|`` (vertical bar), or any control characters (\u0000-\u001f | \u007f - \u009f). Also, it must not contain the literal string quotarnquot.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
.. _Setting Task Priority: http://docs.aws.amazon.com/amazonswf/latest/developerguide/programming-priority.html
