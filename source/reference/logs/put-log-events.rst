[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs put-log-events:


**************
put-log-events
**************



===========
Description
===========



Uploads a batch of log events to the specified log stream. 

 

Every put-log-events request must include the ``sequenceToken`` obtained from the response of the previous request. An upload in a newly created log stream does not require a ``sequenceToken`` . 

 

The batch of events must satisfy the following constraints: 

 
* The maximum batch size is 1,048,576 bytes, and this size is calculated as the sum of all event messages in UTF-8, plus 26 bytes for each log event.
 
* None of the log events in the batch can be more than 2 hours in the future.
 
* None of the log events in the batch can be older than 14 days or the retention period of the log group.
 
* The log events in the batch must be in chronological ordered by their ``timestamp`` .
 
* The maximum number of log events in a batch is 10,000.
 
* A batch of log events in a single put-log-events request cannot span more than 24 hours. Otherwise, the put-log-events operation will fail.
 

 



========
Synopsis
========

::

    put-log-events
  --log-group-name <value>
  --log-stream-name <value>
  --log-events <value>
  [--sequence-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group to put log events to.

  

``--log-stream-name`` (string)


  The name of the log stream to put log events to.

  

``--log-events`` (list)


  A list of log events belonging to a log stream.

  



Shorthand Syntax::

    timestamp=long,message=string ...




JSON Syntax::

  [
    {
      "timestamp": long,
      "message": "string"
    }
    ...
  ]



``--sequence-token`` (string)


  A string token that must be obtained from the response of the previous ``put-log-events`` request. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command puts log events to a log stream named ``20150601`` in the log group ``my-logs``::

  aws logs put-log-events --log-group-name my-logs --log-stream-name 20150601 --log-events file://events

Output::

  {
      "nextSequenceToken": "49542672486831074009579604567656788214806863282469607346"
  }

The above example reads a JSON array of events from a file named ``events`` in the current directory::

  [
    {
      "timestamp": 1433190184356,
      "message": "Example Event 1"
    },
    {
      "timestamp": 1433190184358,
      "message": "Example Event 2"
    },
    {
      "timestamp": 1433190184360,
      "message": "Example Event 3"
    }
  ]

Each subsequent call requires the next sequence token provided by the previous call to be specified with the sequence token option::

  aws logs put-log-events --log-group-name my-logs --log-stream-name 20150601 --log-events file://events2 --sequence-token "49542672486831074009579604567656788214806863282469607346"

Output::

  {
      "nextSequenceToken": "49542672486831074009579604567900991230369019956308219826"
  }


======
Output
======

nextSequenceToken -> (string)

  

  A string token used for making put-log-events requests. A ``sequenceToken`` can only be used once, and put-log-events requests must include the ``sequenceToken`` obtained from the response of the previous request.

  

  

rejectedLogEventsInfo -> (structure)

  

  tooNewLogEventStartIndex -> (integer)

    

    

  tooOldLogEventEndIndex -> (integer)

    

    

  expiredLogEventEndIndex -> (integer)

    

    

  

