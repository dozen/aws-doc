[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf count-closed-workflow-executions:


********************************
count-closed-workflow-executions
********************************



===========
Description
===========



Returns the number of closed workflow executions within the given domain that meet the specified filtering criteria.

 

.. note::

   

  This operation is eventually consistent. The results are best effort and may not exactly reflect recent updates and changes.

   

 

 **Access Control**  

 

You can use IAM policies to control this action's access to Amazon SWF resources as follows:

 

 
* Use a ``Resource`` element with the domain name to limit the action to only specified domains. 
 
* Use an ``Action`` element to allow or deny permission to call this action. 
 
* Constrain the following parameters by using a ``Condition`` element with the appropriate keys. 

   
  * ``tagFilter.tag`` : String constraint. The key is ``swf:tagFilter.tag`` . 
   
  * ``typeFilter.name`` : String constraint. The key is ``swf:typeFilter.name`` . 
   
  * ``typeFilter.version`` : String constraint. The key is ``swf:typeFilter.version`` . 
   

 
 

 

If the caller doesn't have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's ``cause`` parameter is set to ``OPERATION_NOT_PERMITTED`` . For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows <http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html>`_ in the *Amazon SWF Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/swf-2012-01-25/CountClosedWorkflowExecutions>`_


========
Synopsis
========

::

    count-closed-workflow-executions
  --domain <value>
  [--start-time-filter <value>]
  [--close-time-filter <value>]
  [--execution-filter <value>]
  [--type-filter <value>]
  [--tag-filter <value>]
  [--close-status-filter <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain`` (string)


  The name of the domain containing the workflow executions to count.

  

``--start-time-filter`` (structure)


  If specified, only workflow executions that meet the start time criteria of the filter are counted.

   

  .. note::

     

     ``startTimeFilter`` and ``closeTimeFilter`` are mutually exclusive. You must specify one of these in a request but not both.

     

  



Shorthand Syntax::

    oldestDate=timestamp,latestDate=timestamp




JSON Syntax::

  {
    "oldestDate": timestamp,
    "latestDate": timestamp
  }



``--close-time-filter`` (structure)


  If specified, only workflow executions that meet the close time criteria of the filter are counted.

   

  .. note::

     

     ``startTimeFilter`` and ``closeTimeFilter`` are mutually exclusive. You must specify one of these in a request but not both.

     

  



Shorthand Syntax::

    oldestDate=timestamp,latestDate=timestamp




JSON Syntax::

  {
    "oldestDate": timestamp,
    "latestDate": timestamp
  }



``--execution-filter`` (structure)


  If specified, only workflow executions matching the ``WorkflowId`` in the filter are counted.

   

  .. note::

     

     ``closeStatusFilter`` , ``executionFilter`` , ``typeFilter`` and ``tagFilter`` are mutually exclusive. You can specify at most one of these in a request.

     

  



Shorthand Syntax::

    workflowId=string




JSON Syntax::

  {
    "workflowId": "string"
  }



``--type-filter`` (structure)


  If specified, indicates the type of the workflow executions to be counted.

   

  .. note::

     

     ``closeStatusFilter`` , ``executionFilter`` , ``typeFilter`` and ``tagFilter`` are mutually exclusive. You can specify at most one of these in a request.

     

  



Shorthand Syntax::

    name=string,version=string




JSON Syntax::

  {
    "name": "string",
    "version": "string"
  }



``--tag-filter`` (structure)


  If specified, only executions that have a tag that matches the filter are counted.

   

  .. note::

     

     ``closeStatusFilter`` , ``executionFilter`` , ``typeFilter`` and ``tagFilter`` are mutually exclusive. You can specify at most one of these in a request.

     

  



Shorthand Syntax::

    tag=string




JSON Syntax::

  {
    "tag": "string"
  }



``--close-status-filter`` (structure)


  If specified, only workflow executions that match this close status are counted. This filter has an affect only if ``executionStatus`` is specified as ``CLOSED`` .

   

  .. note::

     

     ``closeStatusFilter`` , ``executionFilter`` , ``typeFilter`` and ``tagFilter`` are mutually exclusive. You can specify at most one of these in a request.

     

  



Shorthand Syntax::

    status=string




JSON Syntax::

  {
    "status": "COMPLETED"|"FAILED"|"CANCELED"|"TERMINATED"|"CONTINUED_AS_NEW"|"TIMED_OUT"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

Counting Closed Workflow Executions
-----------------------------------

You can use ``swf count-closed-workflow-executions`` to retrieve the number of closed workflow executions for a given
domain. You can specify filters to count specific classes of executions.

The ``--domain`` and *either* ``--close-time-filter`` or ``--start-time-filter`` arguments are required. All other
arguments are optional.

Here is a basic example::

    aws swf count-closed-workflow-executions --domain DataFrobtzz --close-time-filter "{ \"latestDate\" : 1377129600, \"oldestDate\" : 1370044800 }"

Result::

    {
        "count": 2,
        "truncated": false
    }

If "truncated" is ``true``, then "count" represents the maximum number that can be returned by Amazon SWF. Any further
results are truncated.

To reduce the number of results returned, you can:

-  modify the ``--close-time-filter`` or ``--start-time-filter`` values to narrow the time range that is searched. Each
    of these is mutually exclusive: You can specify *only one of these* in a request.

-  use the ``--close-status-filter``, ``--execution-filter``, ``--tag-filter`` or ``--type-filter`` arguments to further
    filter the results. However, these arguments are also mutually exclusive.

See Also
--------

-  `CountClosedWorkflowExecutions <http://docs.aws.amazon.com/amazonswf/latest/apireference/API_CountClosedWorkflowExecutions.html>`_ in the *Amazon Simple Workflow Service API Reference*



======
Output
======

count -> (integer)

  

  The number of workflow executions.

  

  

truncated -> (boolean)

  

  If set to true, indicates that the actual count was more than the maximum supported by this API and the count returned is the truncated value.

  

  

