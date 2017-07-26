[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda create-event-source-mapping:


***************************
create-event-source-mapping
***************************



===========
Description
===========



Identifies a stream as an event source for a Lambda function. It can be either an Amazon Kinesis stream or an Amazon DynamoDB stream. AWS Lambda invokes the specified function when records are posted to the stream.

 

This association between a stream source and a Lambda function is called the event source mapping.

 

.. warning::

   

  This event source mapping is relevant only in the AWS Lambda pull model, where AWS Lambda invokes the function. For more information, see `AWS Lambda\: How it Works <http://docs.aws.amazon.com/lambda/latest/dg/lambda-introduction.html>`_ in the *AWS Lambda Developer Guide* .

   

 

You provide mapping information (for example, which stream to read from and which Lambda function to invoke) in the request body.

 

Each event source, such as an Amazon Kinesis or a DynamoDB stream, can be associated with multiple AWS Lambda function. A given Lambda function can be associated with multiple AWS event sources.

 

If you are using versioning, you can specify a specific function version or an alias via the function name parameter. For more information about versioning, see `AWS Lambda Function Versioning and Aliases <http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html>`_ . 

 

This operation requires permission for the ``lambda:CreateEventSourceMapping`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/CreateEventSourceMapping>`_


========
Synopsis
========

::

    create-event-source-mapping
  --event-source-arn <value>
  --function-name <value>
  [--enabled | --no-enabled]
  [--batch-size <value>]
  --starting-position <value>
  [--starting-position-timestamp <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--event-source-arn`` (string)


  The Amazon Resource Name (ARN) of the Amazon Kinesis or the Amazon DynamoDB stream that is the event source. Any record added to this stream could cause AWS Lambda to invoke your Lambda function, it depends on the ``batch-size`` . AWS Lambda POSTs the Amazon Kinesis event, containing records, to your Lambda function as JSON.

  

``--function-name`` (string)


  The Lambda function to invoke when AWS Lambda detects an event on the stream.

   

  You can specify the function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). 

   

  If you are using versioning, you can also provide a qualified function ARN (ARN that is qualified with function version or alias name as suffix). For more information about versioning, see `AWS Lambda Function Versioning and Aliases <http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html>`_  

   

  AWS Lambda also allows you to specify only the function name with the account ID qualifier (for example, ``account-id:Thumbnail`` ). 

   

  Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 characters in length.

  

``--enabled`` | ``--no-enabled`` (boolean)


  Indicates whether AWS Lambda should begin polling the event source. By default, ``enabled`` is true. 

  

``--batch-size`` (integer)


  The largest number of records that AWS Lambda will retrieve from your event source at the time of invoking your function. Your function receives an event with all the retrieved records. The default is 100 records.

  

``--starting-position`` (string)


  The position in the stream where AWS Lambda should start reading. Valid only for Kinesis streams. For more information, see `ShardIteratorType <http://docs.aws.amazon.com/kinesis/latest/APIReference/API_GetShardIterator.html#Kinesis-GetShardIterator-request-ShardIteratorType>`_ in the *Amazon Kinesis API Reference* . 

  

  Possible values:

  
  *   ``TRIM_HORIZON``

  
  *   ``LATEST``

  
  *   ``AT_TIMESTAMP``

  

  

``--starting-position-timestamp`` (timestamp)


  The timestamp of the data record from which to start reading. Used with `shard iterator type <http://docs.aws.amazon.com/kinesis/latest/APIReference/API_GetShardIterator.html#Kinesis-GetShardIterator-request-ShardIteratorType>`_ AT_TIMESTAMP. If a record with this exact timestamp does not exist, the iterator returned is for the next (later) record. If the timestamp is older than the current trim horizon, the iterator returned is for the oldest untrimmed data record (TRIM_HORIZON). Valid only for Kinesis streams. 

  

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

  

  The state of the event source mapping. It can be ``Creating`` , ``enabled`` , ``Disabled`` , ``Enabling`` , ``Disabling`` , ``Updating`` , or ``Deleting`` .

  

  

StateTransitionReason -> (string)

  

  The reason the event source mapping is in its current state. It is either user-requested or an AWS Lambda-initiated state transition.

  

  

