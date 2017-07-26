[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf count-pending-decision-tasks:


****************************
count-pending-decision-tasks
****************************



===========
Description
===========



Returns the estimated number of decision tasks in the specified task list. The count returned is an approximation and isn't guaranteed to be exact. If you specify a task list that no decision task was ever scheduled in then ``0`` is returned.

 

 **Access Control**  

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains. 
 
* Use an ``Action`` element to allow or deny permission to call this action. 
 
* Constrain the ``taskList.name`` parameter by using a ``Condition`` element with the ``swf:taskList.name`` key to allow the action to access only certain task lists. 
 

 

If the caller doesn't have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's ``cause`` parameter is set to ``OPERATION_NOT_PERMITTED`` . For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows <http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html>`_ in the *Amazon SWF Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/swf-2012-01-25/CountPendingDecisionTasks>`_


========
Synopsis
========

::

    count-pending-decision-tasks
  --domain <value>
  --task-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

count -> (integer)

  

  The number of tasks in the task list.

  

  

truncated -> (boolean)

  

  If set to true, indicates that the actual count was more than the maximum supported by this API and the count returned is the truncated value.

  

  

