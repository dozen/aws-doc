[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda list-event-source-mappings:


**************************
list-event-source-mappings
**************************



===========
Description
===========



Returns a list of event source mappings you created using the ``create-event-source-mapping`` (see  create-event-source-mapping ). 

 

For each mapping, the API returns configuration information. You can optionally specify filters to retrieve specific event source mappings.

 

If you are using the versioning feature, you can get list of event source mappings for a specific Lambda function version or an alias as described in the ``function-name`` parameter. For information about the versioning feature, see `AWS Lambda Function Versioning and Aliases <http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html>`_ . 

 

This operation requires permission for the ``lambda:ListEventSourceMappings`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lambda-2015-03-31/ListEventSourceMappings>`_


``list-event-source-mappings`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``EventSourceMappings``


========
Synopsis
========

::

    list-event-source-mappings
  [--event-source-arn <value>]
  [--function-name <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--event-source-arn`` (string)


  The Amazon Resource Name (ARN) of the Amazon Kinesis stream. (This parameter is optional.)

  

``--function-name`` (string)


  The name of the Lambda function.

   

  You can specify the function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). If you are using versioning, you can also provide a qualified function ARN (ARN that is qualified with function version or alias name as suffix). AWS Lambda also allows you to specify only the function name with the account ID qualifier (for example, ``account-id:Thumbnail`` ). Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 characters in length. 

  

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextMarker -> (string)

  

  A string, present if there are more event source mappings.

  

  

EventSourceMappings -> (list)

  

  An array of ``EventSourceMappingConfiguration`` objects.

  

  (structure)

    

    Describes mapping between an Amazon Kinesis stream and a Lambda function.

    

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

      

      

    

  

