[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda delete-event-source-mapping:


***************************
delete-event-source-mapping
***************************



===========
Description
===========



Removes an event source mapping. This means AWS Lambda will no longer invoke the function for events in the associated source.

 

This operation requires permission for the ``lambda:DeleteEventSourceMapping`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/DeleteEventSourceMapping>`_


========
Synopsis
========

::

    delete-event-source-mapping
  --uuid <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--uuid`` (string)


  The event source mapping ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

