[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf count-pending-activity-tasks:


****************************
count-pending-activity-tasks
****************************



===========
Description
===========



Returns the estimated number of activity tasks in the specified task list. The count returned is an approximation and is not guaranteed to be exact. If you specify a task list that no activity task was ever scheduled in then 0 will be returned.

 

**Access Control** 

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains.
 
* Use an ``Action`` element to allow or deny permission to call this action.
 
* Constrain the ``taskList.name`` parameter by using a **Condition** element with the ``swf:taskList.name`` key to allow the action to access only certain task lists.
 

 

If the caller does not have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's **cause** parameter will be set to OPERATION_NOT_PERMITTED. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .



========
Synopsis
========

::

    count-pending-activity-tasks
  --domain <value>
  --task-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain that contains the task list.

  

``--task-list`` (structure)


  The name of the task list.

  



Shorthand Syntax::

    name=string




JSON Syntax::

  {
    "name": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

count -> (integer)

  

  The number of tasks in the task list.

  

  

truncated -> (boolean)

  

  If set to true, indicates that the actual count was more than the maximum supported by this API and the count returned is the truncated value.

  

  



.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
