[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf count-open-workflow-executions:


******************************
count-open-workflow-executions
******************************



===========
Description
===========



Returns the number of open workflow executions within the given domain that meet the specified filtering criteria.

 

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
   

 
 

 

If the caller does not have sufficient permissions to invoke the action, or the parameter values fall outside the specified constraints, the action fails. The associated event attribute's **cause** parameter will be set to OPERATION_NOT_PERMITTED. For details and example IAM policies, see `Using IAM to Manage Access to Amazon SWF Workflows`_ .



========
Synopsis
========

::

    count-open-workflow-executions
  --domain <value>
  --start-time-filter <value>
  [--type-filter <value>]
  [--tag-filter <value>]
  [--execution-filter <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain`` (string)


  The name of the domain containing the workflow executions to count.

  

``--start-time-filter`` (structure)


  Specifies the start time criteria that workflow executions must meet in order to be counted.

  



Shorthand Syntax::

    oldestDate=timestamp,latestDate=timestamp




JSON Syntax::

  {
    "oldestDate": timestamp,
    "latestDate": timestamp
  }



``--type-filter`` (structure)


  Specifies the type of the workflow executions to be counted.

   

  .. note::

    ``executionFilter`` , ``typeFilter`` and ``tagFilter`` are mutually exclusive. You can specify at most one of these in a request.

  



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

    ``executionFilter`` , ``typeFilter`` and ``tagFilter`` are mutually exclusive. You can specify at most one of these in a request.

  



Shorthand Syntax::

    tag=string




JSON Syntax::

  {
    "tag": "string"
  }



``--execution-filter`` (structure)


  If specified, only workflow executions matching the ``WorkflowId`` in the filter are counted.

   

  .. note::

    ``executionFilter`` , ``typeFilter`` and ``tagFilter`` are mutually exclusive. You can specify at most one of these in a request.

  



Shorthand Syntax::

    workflowId=string




JSON Syntax::

  {
    "workflowId": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**Counting Open Workflow Executions**

You can use ``swf count-open-workflow-executions`` to retrieve the number of open workflow executions for a given
domain. You can specify filters to count specific classes of executions.

The ``--domain`` and ``--start-time-filter`` arguments are required. All other arguments are optional.

Here is a basic example::

  aws swf count-open-workflow-executions --domain DataFrobtzz --start-time-filter "{ \"latestDate\" : 1377129600, \"oldestDate\" : 1370044800 }"

Result::

  {
    "count": 4,
    "truncated": false
  }

If "truncated" is ``true``, then "count" represents the maximum number that can be returned by Amazon SWF. Any further
results are truncated.

To reduce the number of results returned, you can:

-  modify the ``--start-time-filter`` values to narrow the time range that is searched.

-  use the ``--close-status-filter``, ``--execution-filter``, ``--tag-filter`` or ``--type-filter`` arguments to further
    filter the results. Each of these is mutually exclusive: You can specify *only one of these* in a request.

For more information, see `CountOpenWorkflowExecutions`_ in the *Amazon Simple Workflow Service API Reference*

.. _`CountOpenWorkflowExecutions`: http://docs.aws.amazon.com/amazonswf/latest/apireference/API_CountOpenWorkflowExecutions.html



======
Output
======

count -> (integer)

  

  The number of workflow executions.

  

  

truncated -> (boolean)

  

  If set to true, indicates that the actual count was more than the maximum supported by this API and the count returned is the truncated value.

  

  



.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
