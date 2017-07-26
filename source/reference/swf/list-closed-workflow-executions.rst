[ :ref:`aws <cli:aws>` . :ref:`swf <cli:aws swf>` ]

.. _cli:aws swf list-closed-workflow-executions:


*******************************
list-closed-workflow-executions
*******************************



===========
Description
===========



Returns a list of closed workflow executions in the specified domain that meet the filtering criteria. The results may be split into multiple pages. To retrieve subsequent pages, make the call again using the nextPageToken returned by the initial call.

 

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



``list-closed-workflow-executions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``executionInfos``


========
Synopsis
========

::

    list-closed-workflow-executions
  --domain <value>
  [--start-time-filter <value>]
  [--close-time-filter <value>]
  [--execution-filter <value>]
  [--close-status-filter <value>]
  [--type-filter <value>]
  [--tag-filter <value>]
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


  The name of the domain that contains the workflow executions to list.

  

``--start-time-filter`` (structure)


  If specified, the workflow executions are included in the returned results based on whether their start times are within the range specified by this filter. Also, if this parameter is specified, the returned results are ordered by their start times.

   

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


  If specified, the workflow executions are included in the returned results based on whether their close times are within the range specified by this filter. Also, if this parameter is specified, the returned results are ordered by their close times.

   

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


  If specified, only workflow executions matching the workflow ID specified in the filter are returned.

   

  .. note::

    ``closeStatusFilter`` , ``executionFilter`` , ``typeFilter`` and ``tagFilter`` are mutually exclusive. You can specify at most one of these in a request.

  



Shorthand Syntax::

    workflowId=string




JSON Syntax::

  {
    "workflowId": "string"
  }



``--close-status-filter`` (structure)


  If specified, only workflow executions that match this *close status* are listed. For example, if TERMINATED is specified, then only TERMINATED workflow executions are listed.

   

  .. note::

    ``closeStatusFilter`` , ``executionFilter`` , ``typeFilter`` and ``tagFilter`` are mutually exclusive. You can specify at most one of these in a request.

  



Shorthand Syntax::

    status=string




JSON Syntax::

  {
    "status": "COMPLETED"|"FAILED"|"CANCELED"|"TERMINATED"|"CONTINUED_AS_NEW"|"TIMED_OUT"
  }



``--type-filter`` (structure)


  If specified, only executions of the type specified in the filter are returned.

   

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


  If specified, only executions that have the matching tag are listed.

   

  .. note::

    ``closeStatusFilter`` , ``executionFilter`` , ``typeFilter`` and ``tagFilter`` are mutually exclusive. You can specify at most one of these in a request.

  



Shorthand Syntax::

    tag=string




JSON Syntax::

  {
    "tag": "string"
  }



``--reverse-order`` | ``--no-reverse-order`` (boolean)


  When set to ``true`` , returns the results in reverse order. By default the results are returned in descending order of the start or the close time of the executions.

  

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

executionInfos -> (list)

  

  The list of workflow information structures.

  

  (structure)

    

    Contains information about a workflow execution. 

    

    execution -> (structure)

      

      The workflow execution this information is about.

      

      workflowId -> (string)

        

        The user defined identifier associated with the workflow execution.

        

        

      runId -> (string)

        

        A system-generated unique identifier for the workflow execution.

        

        

      

    workflowType -> (structure)

      

      The type of the workflow execution.

      

      name -> (string)

        

        **Required.** The name of the workflow type.

         

        .. note::

          The combination of workflow type name and version must be unique with in a domain.

        

        

      version -> (string)

        

        **Required.** The version of the workflow type.

         

        .. note::

          The combination of workflow type name and version must be unique with in a domain.

        

        

      

    startTimestamp -> (timestamp)

      

      The time when the execution was started.

      

      

    closeTimestamp -> (timestamp)

      

      The time when the workflow execution was closed. Set only if the execution status is CLOSED.

      

      

    executionStatus -> (string)

      

      The current status of the execution.

      

      

    closeStatus -> (string)

      

      If the execution status is closed then this specifies how the execution was closed:

       

       
      * ``COMPLETED`` : the execution was successfully completed.
       
      * ``CANCELED`` : the execution was canceled.Cancellation allows the implementation to gracefully clean up before the execution is closed.
       
      * ``TERMINATED`` : the execution was force terminated.
       
      * ``FAILED`` : the execution failed to complete.
       
      * ``TIMED_OUT`` : the execution did not complete in the alloted time and was automatically timed out.
       
      * ``CONTINUED_AS_NEW`` : the execution is logically continued. This means the current execution was completed and a new execution was started to carry on the workflow.
       

      

      

    parent -> (structure)

      

      If this workflow execution is a child of another execution then contains the workflow execution that started this execution.

      

      workflowId -> (string)

        

        The user defined identifier associated with the workflow execution.

        

        

      runId -> (string)

        

        A system-generated unique identifier for the workflow execution.

        

        

      

    tagList -> (list)

      

      The list of tags associated with the workflow execution. Tags can be used to identify and list workflow executions of interest through the visibility APIs. A workflow execution can have a maximum of 5 tags.

      

      (string)

        

        

      

    cancelRequested -> (boolean)

      

      Set to true if a cancellation is requested for this workflow execution.

      

      

    

  

nextPageToken -> (string)

  

  If a ``NextPageToken`` was returned by a previous call, there are more results available. To retrieve the next page of results, make the call again using the returned token in ``nextPageToken`` . Keep all other arguments unchanged.

   

  The configured ``maximumPageSize`` determines how many results can be returned in a single call.

  

  



.. _Using IAM to Manage Access to Amazon SWF Workflows: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-iam.html
