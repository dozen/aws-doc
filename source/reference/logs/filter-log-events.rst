[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs filter-log-events:


*****************
filter-log-events
*****************



===========
Description
===========



Lists log events from the specified log group. You can list all the log events or filter the results using a filter pattern, a time range, and the name of the log stream.

 

By default, this operation returns as many log events as can fit in 1MB (up to 10,000 log events), or all the events found within the time range that you specify. If the results include a token, then there are more log events available, and you can get additional results by specifying the token in a subsequent call.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/FilterLogEvents>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group.

  

``--log-stream-names`` (list)


  Optional list of log stream names.

  



Syntax::

  "string" "string" ...



``--start-time`` (long)


  The start of the time range, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp prior to this time are not returned.

  

``--end-time`` (long)


  The end of the time range, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp later than this time are not returned.

  

``--filter-pattern`` (string)


  The filter pattern to use. If not provided, all the events are matched.

  

``--interleaved`` | ``--no-interleaved`` (boolean)


  If the value is true, the operation makes a best effort to provide responses that contain events from multiple log streams within the log group interleaved in a single response. If the value is false all the matched log events in the first log stream are searched first, then those in the next log stream, and so on. The default is false.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

events -> (list)

  

  The matched events.

  

  (structure)

    

    Represents a matched event.

    

    logStreamName -> (string)

      

      The name of the log stream this event belongs to.

      

      

    timestamp -> (long)

      

      The time the event occurred, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    message -> (string)

      

      The data contained in the log event.

      

      

    ingestionTime -> (long)

      

      The time the event was ingested, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    eventId -> (string)

      

      The ID of the event.

      

      

    

  

searchedLogStreams -> (list)

  

  Indicates which log streams have been searched and whether each has been searched completely.

  

  (structure)

    

    Represents the search status of a log stream.

    

    logStreamName -> (string)

      

      The name of the log stream.

      

      

    searchedCompletely -> (boolean)

      

      Indicates whether all the events in this log stream were searched.

      

      

    

  

nextToken -> (string)

  

  The token to use when requesting the next set of items. The token expires after 24 hours.

  

  

