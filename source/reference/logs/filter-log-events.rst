[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs filter-log-events:


*****************
filter-log-events
*****************



===========
Description
===========



Retrieves log events, optionally filtered by a filter pattern from the specified log group. You can provide an optional time range to filter the results on the event ``timestamp`` . You can limit the streams searched to an explicit list of ``logStreamNames`` . 

 

By default, this operation returns as much matching log events as can fit in a response size of 1MB, up to 10,000 log events, or all the events found within a time-bounded scan window. If the response includes a ``nextToken`` , then there is more data to search, and the search can be resumed with a new request providing the nextToken. The response will contain a list of ``searchedLogStreams`` that contains information about which streams were searched in the request and whether they have been searched completely or require further pagination. The ``limit`` parameter in the request. can be used to specify the maximum number of events to return in a page. 



``filter-log-events`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``events``, ``searchedLogStreams``


========
Synopsis
========

::

    filter-log-events
  --log-group-name <value>
  [--log-stream-names <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--filter-pattern <value>]
  [--interleaved | --no-interleaved]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group to query. 

  

``--log-stream-names`` (list)


  Optional list of log stream names within the specified log group to search. Defaults to all the log streams in the log group. 

  



Syntax::

  "string" "string" ...



``--start-time`` (long)


  A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. If provided, events with a timestamp prior to this time are not returned.

  

``--end-time`` (long)


  A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. If provided, events with a timestamp later than this time are not returned.

  

``--filter-pattern`` (string)


  A valid CloudWatch Logs filter pattern to use for filtering the response. If not provided, all the events are matched. 

  

``--interleaved`` | ``--no-interleaved`` (boolean)


  If provided, the API will make a best effort to provide responses that contain events from multiple log streams within the log group interleaved in a single response. If not provided, all the matched log events in the first log stream will be searched first, then those in the next log stream, etc.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

events -> (list)

  

  A list of ``FilteredLogEvent`` objects representing the matched events from the request.

  

  (structure)

    

    Represents a matched event from a ``filter-log-events`` request.

    

    logStreamName -> (string)

      

      The name of the log stream this event belongs to.

      

      

    timestamp -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    message -> (string)

      

      The data contained in the log event.

      

      

    ingestionTime -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    eventId -> (string)

      

      A unique identifier for this event.

      

      

    

  

searchedLogStreams -> (list)

  

  A list of ``SearchedLogStream`` objects indicating which log streams have been searched in this request and whether each has been searched completely or still has more to be paginated.

  

  (structure)

    

    An object indicating the search status of a log stream in a ``filter-log-events`` request.

    

    logStreamName -> (string)

      

      The name of the log stream.

      

      

    searchedCompletely -> (boolean)

      

      Indicates whether all the events in this log stream were searched or more data exists to search by paginating further.

      

      

    

  

nextToken -> (string)

  

  A pagination token obtained from a ``filter-log-events`` response to continue paginating the filter-log-events results. This token is omitted from the response when there are no other events to display.

  

  

