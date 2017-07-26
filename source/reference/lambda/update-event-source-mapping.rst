[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda update-event-source-mapping:


***************************
update-event-source-mapping
***************************



===========
Description
===========



You can update an event source mapping. This is useful if you want to change the parameters of the existing mapping without losing your position in the stream. You can change which function will receive the stream records, but to change the stream itself, you must create a new mapping.

 

If you are using the versioning feature, you can update the event source mapping to map to a specific Lambda function version or alias as described in the ``function-name`` parameter. For information about the versioning feature, see `AWS Lambda Function Versioning and Aliases <http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html>`_ . 

 

If you disable the event source mapping, AWS Lambda stops polling. If you enable again, it will resume polling from the time it had stopped polling, so you don't lose processing of any records. However, if you delete event source mapping and create it again, it will reset.

 

This operation requires permission for the ``lambda:UpdateEventSourceMapping`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/UpdateEventSourceMapping>`_


========
Synopsis
========

::

    update-event-source-mapping
  --uuid <value>
  [--function-name <value>]
  [--enabled | --no-enabled]
  [--batch-size <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--uuid`` (string)


  The event source mapping identifier.

  

``--function-name`` (string)


  The Lambda function to which you want the stream records sent.

   

  You can specify a function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). AWS Lambda also allows you to specify a partial ARN (for example, ``account-id:Thumbnail`` ). Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 characters in length. 

   

  If you are using versioning, you can also provide a qualified function ARN (ARN that is qualified with function version or alias name as suffix). For more information about versioning, see `AWS Lambda Function Versioning and Aliases <http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html>`_  

   

  Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 character in length.

  

``--enabled`` | ``--no-enabled`` (boolean)


  Specifies whether AWS Lambda should actively poll the stream or not. If disabled, AWS Lambda will not poll the stream.

  

``--batch-size`` (integer)


  The maximum number of stream records that can be sent to your Lambda function for a single invocation.

  

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

  

  

