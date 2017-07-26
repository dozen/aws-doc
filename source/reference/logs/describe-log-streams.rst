[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs describe-log-streams:


********************
describe-log-streams
********************



===========
Description
===========



Returns all the log streams that are associated with the specified log group. The list returned in the response is ASCII-sorted by log stream name. 

 

By default, this operation returns up to 50 log streams. If there are more log streams to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of log streams returned in the response by specifying the ``limit`` parameter in the request. This operation has a limit of five transactions per second, after which transactions are throttled. 



``describe-log-streams`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``logStreams``


========
Synopsis
========

::

    describe-log-streams
  --log-group-name <value>
  [--log-stream-name-prefix <value>]
  [--order-by <value>]
  [--descending | --no-descending]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The log group name for which log streams are to be listed.

  

``--log-stream-name-prefix`` (string)


  Will only return log streams that match the provided logStreamNamePrefix. If you don't specify a value, no prefix filter is applied. 

  

``--order-by`` (string)


  Specifies what to order the returned log streams by. Valid arguments are 'LogStreamName' or 'LastEventTime'. If you don't specify a value, results are ordered by LogStreamName. If 'LastEventTime' is chosen, the request cannot also contain a logStreamNamePrefix. 

  

  Possible values:

  
  *   ``LogStreamName``

  
  *   ``LastEventTime``

  

  

``--descending`` | ``--no-descending`` (boolean)


  If set to true, results are returned in descending order. If you don't specify a value or set it to false, results are returned in ascending order. 

  

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



========
Examples
========

The following command shows all log streams starting with the prefix ``2015`` in the log group ``my-logs``::

  aws logs describe-log-streams --log-group-name my-logs --log-stream-name-prefix 2015

Output::

  {
      "logStreams": [
          {
              "creationTime": 1433189871774,
              "arn": "arn:aws:logs:us-west-2:0123456789012:log-group:my-logs:log-stream:20150531",
              "logStreamName": "20150531",
              "storedBytes": 0
          },
          {
              "creationTime": 1433189873898,
              "arn": "arn:aws:logs:us-west-2:0123456789012:log-group:my-logs:log-stream:20150601",
              "logStreamName": "20150601",
              "storedBytes": 0
          }
      ]
  }


======
Output
======

logStreams -> (list)

  

  A list of log streams.

  

  (structure)

    

    A log stream is sequence of log events from a single emitter of logs.

    

    logStreamName -> (string)

      

      

    creationTime -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    firstEventTimestamp -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    lastEventTimestamp -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    lastIngestionTime -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    uploadSequenceToken -> (string)

      

      A string token used for making put-log-events requests. A ``sequenceToken`` can only be used once, and put-log-events requests must include the ``sequenceToken`` obtained from the response of the previous request.

      

      

    arn -> (string)

      

      

    storedBytes -> (long)

      

      

    

  

nextToken -> (string)

  

  A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

  

  

