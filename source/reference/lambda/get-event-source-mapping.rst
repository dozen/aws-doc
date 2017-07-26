[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda get-event-source-mapping:


************************
get-event-source-mapping
************************



===========
Description
===========



Returns configuration information for the specified event source mapping (see  create-event-source-mapping ).

 

This operation requires permission for the ``lambda:GetEventSourceMapping`` action.



========
Synopsis
========

::

    get-event-source-mapping
  --uuid <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--uuid`` (string)


  The AWS Lambda assigned ID of the event source mapping.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

UUID -> (string)

  

  The AWS Lambda assigned opaque identifier for the mapping.

  

  

BatchSize -> (integer)

  

  The largest number of records that AWS Lambda will retrieve from your event source at the time of invoking your function. Your function receives an event with all the retrieved records.

  

  

EventSourceArn -> (string)

  

  The Amazon Resource Name (ARN) of the Amazon Kinesis stream that is the source of events.

  

  

FunctionArn -> (string)

  

  The Lambda function to invoke when AWS Lambda detects an event on the stream.

  

  

LastModified -> (timestamp)

  

  The UTC time string indicating the last time the event mapping was updated.

  

  

LastProcessingResult -> (string)

  

  The result of the last AWS Lambda invocation of your Lambda function.

  

  

State -> (string)

  

  The state of the event source mapping. It can be ``Creating`` , ``Enabled`` , ``Disabled`` , ``Enabling`` , ``Disabling`` , ``Updating`` , or ``Deleting`` .

  

  

StateTransitionReason -> (string)

  

  The reason the event source mapping is in its current state. It is either user-requested or an AWS Lambda-initiated state transition.

  

  

