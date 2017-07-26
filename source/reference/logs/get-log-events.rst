[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs get-log-events:


**************
get-log-events
**************



===========
Description
===========



Lists log events from the specified log stream. You can list all the log events or filter using a time range.

 

By default, this operation returns as many log events as can fit in a response size of 1MB (up to 10,000 log events). If the results include tokens, there are more log events available. You can get additional log events by specifying one of the tokens in a subsequent call.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/GetLogEvents>`_


========
Synopsis
========

::

    get-log-events
  --log-group-name <value>
  --log-stream-name <value>
  [--start-time <value>]
  [--end-time <value>]
  [--next-token <value>]
  [--limit <value>]
  [--start-from-head | --no-start-from-head]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group.

  

``--log-stream-name`` (string)


  The name of the log stream.

  

``--start-time`` (long)


  The start of the time range, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp earlier than this time are not included.

  

``--end-time`` (long)


  The end of the time range, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC. Events with a timestamp later than this time are not included.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--limit`` (integer)


  The maximum number of log events returned. If you don't specify a value, the maximum is as many log events as can fit in a response size of 1MB, up to 10,000 log events.

  

``--start-from-head`` | ``--no-start-from-head`` (boolean)


  If the value is true, the earliest log events are returned first. If the value is false, the latest log events are returned first. The default value is false.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command retrieves log events from a log stream named ``20150601`` in the log group ``my-logs``::

  aws logs get-log-events --log-group-name my-logs --log-stream-name 20150601

Output::

  {
      "nextForwardToken": "f/31961209122447488583055879464742346735121166569214640130",
      "events": [
          {
              "ingestionTime": 1433190494190,
              "timestamp": 1433190184356,
              "message": "Example Event 1"
          },
          {
              "ingestionTime": 1433190516679,
              "timestamp": 1433190184356,
              "message": "Example Event 1"
          },
          {
              "ingestionTime": 1433190494190,
              "timestamp": 1433190184358,
              "message": "Example Event 2"
          }
      ],
      "nextBackwardToken": "b/31961209122358285602261756944988674324553373268216709120"
  }


======
Output
======

events -> (list)

  

  The events.

  

  (structure)

    

    Represents a log event.

    

    timestamp -> (long)

      

      The time the event occurred, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    message -> (string)

      

      The data contained in the log event.

      

      

    ingestionTime -> (long)

      

      The time the event was ingested, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    

  

nextForwardToken -> (string)

  

  The token for the next set of items in the forward direction. The token expires after 24 hours.

  

  

nextBackwardToken -> (string)

  

  The token for the next set of items in the backward direction. The token expires after 24 hours.

  

  

