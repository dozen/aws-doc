[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs get-log-events:


**************
get-log-events
**************



===========
Description
===========



Retrieves log events from the specified log stream. You can provide an optional time range to filter the results on the event ``timestamp`` . 

 

By default, this operation returns as much log events as can fit in a response size of 1MB, up to 10,000 log events. The response will always include a ``nextForwardToken`` and a ``nextBackwardToken`` in the response body. You can use any of these tokens in subsequent ``get-log-events`` requests to paginate through events in either forward or backward direction. You can also limit the number of log events returned in the response by specifying the ``limit`` parameter in the request. 



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
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group to query.

  

``--log-stream-name`` (string)


  The name of the log stream to query.

  

``--start-time`` (long)


  A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

  

``--end-time`` (long)


  A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

  

``--next-token`` (string)


  A string token used for pagination that points to the next page of results. It must be a value obtained from the ``nextForwardToken`` or ``nextBackwardToken`` fields in the response of the previous ``get-log-events`` request. 

  

``--limit`` (integer)


  The maximum number of log events returned in the response. If you don't specify a value, the request would return as many log events as can fit in a response size of 1MB, up to 10,000 log events. 

  

``--start-from-head`` | ``--no-start-from-head`` (boolean)


  If set to true, the earliest log events would be returned first. The default is false (the latest log events are returned first).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  (structure)

    

    timestamp -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    message -> (string)

      

      

    ingestionTime -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    

  

nextForwardToken -> (string)

  

  A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

  

  

nextBackwardToken -> (string)

  

  A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

  

  

