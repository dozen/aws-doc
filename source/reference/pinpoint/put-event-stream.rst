[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint put-event-stream:


****************
put-event-stream
****************



===========
Description
===========

Use to create or update the event stream for an app.

========
Synopsis
========

::

    put-event-stream
  --application-id <value>
  --write-event-stream <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)
ApplicationId

``--write-event-stream`` (structure)
EventStream to write.



Shorthand Syntax::

    DestinationStreamArn=string,ExternalId=string,RoleArn=string




JSON Syntax::

  {
    "DestinationStreamArn": "string",
    "ExternalId": "string",
    "RoleArn": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EventStream -> (structure)

  Model for an event publishing subscription export.

  ApplicationId -> (string)

    The ID of the application from which events should be published.

    

  DestinationStreamArn -> (string)

    The Amazon Resource Name (ARN) of the Amazon Kinesis stream or Firehose delivery stream to which you want to publish events. Firehose ARN: arn:aws:firehose:REGION:ACCOUNT_ID:deliverystream/STREAM_NAME Kinesis ARN: arn:aws:kinesis:REGION:ACCOUNT_ID:stream/STREAM_NAME

    

  ExternalId -> (string)

    The external ID assigned the IAM role that authorizes Amazon Pinpoint to publish to the stream.

    

  LastModifiedDate -> (string)

    The date the event stream was last updated in ISO 8601 format.

    

  LastUpdatedBy -> (string)

    The IAM user who last modified the event stream.

    

  RoleArn -> (string)

    The IAM role that authorizes Amazon Pinpoint to publish events to the stream in your account.

    

  

