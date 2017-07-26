[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs describe-log-streams:


********************
describe-log-streams
********************



===========
Description
===========



Lists the log streams for the specified log group. You can list all the log streams or filter the results by prefix. You can also control how the results are ordered.

 

This operation has a limit of five transactions per second, after which transactions are throttled.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/DescribeLogStreams>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group.

  

``--log-stream-name-prefix`` (string)


  The prefix to match.

   

  You cannot specify this parameter if ``orderBy`` is ``LastEventTime`` .

  

``--order-by`` (string)


  If the value is ``log-stream-name-prefix`` , the results are ordered by log stream name. If the value is ``LastEventTime`` , the results are ordered by the event time. The default value is ``log-stream-name-prefix`` .

   

  If you order the results by event time, you cannot specify the ``logStreamNamePrefix`` parameter.

   

  lastEventTimestamp represents the time of the most recent log event in the log stream in CloudWatch Logs. This number is expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. lastEventTimeStamp updates on an eventual consistency basis. It typically updates in less than an hour from ingestion, but may take longer in some rare situations.

  

  Possible values:

  
  *   ``LogStreamName``

  
  *   ``LastEventTime``

  

  

``--descending`` | ``--no-descending`` (boolean)


  If the value is true, results are returned in descending order. If the value is to false, results are returned in ascending order. The default value is false.

  

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

  

  The log streams.

  

  (structure)

    

    Represents a log stream, which is a sequence of log events from a single emitter of logs.

    

    logStreamName -> (string)

      

      The name of the log stream.

      

      

    creationTime -> (long)

      

      The creation time of the stream, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    firstEventTimestamp -> (long)

      

      The time of the first event, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    lastEventTimestamp -> (long)

      

      the time of the most recent log event in the log stream in CloudWatch Logs. This number is expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. lastEventTime updates on an eventual consistency basis. It typically updates in less than an hour from ingestion, but may take longer in some rare situations.

      

      

    lastIngestionTime -> (long)

      

      The ingestion time, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    uploadSequenceToken -> (string)

      

      The sequence token.

      

      

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the log stream.

      

      

    storedBytes -> (long)

      

      The number of bytes stored.

      

      

    

  

nextToken -> (string)

  

  The token for the next set of items to return. The token expires after 24 hours.

  

  

