[ :ref:`aws <cli:aws>` . :ref:`dynamodbstreams <cli:aws dynamodbstreams>` ]

.. _cli:aws dynamodbstreams list-streams:


************
list-streams
************



===========
Description
===========



Returns an array of stream ARNs associated with the current account and endpoint. If the ``table-name`` parameter is present, then *list-streams* will return only the streams ARNs for that table.

 

.. note::

  

  You can call *list-streams* at a maximum rate of 5 times per second.

  



========
Synopsis
========

::

    list-streams
  [--table-name <value>]
  [--limit <value>]
  [--exclusive-start-stream-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--table-name`` (string)


  If this parameter is provided, then only the streams associated with this table name are returned.

  

``--limit`` (integer)


  The maximum number of streams to return. The upper limit is 100.

  

``--exclusive-start-stream-arn`` (string)


  The ARN (Amazon Resource Name) of the first item that this operation will evaluate. Use the value that was returned for ``LastEvaluatedStreamArn`` in the previous operation. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Streams -> (list)

  

  A list of stream descriptors associated with the current account and endpoint.

  

  (structure)

    

    Represents all of the data describing a particular stream.

    

    StreamArn -> (string)

      

      The Amazon Resource Name (ARN) for the stream.

      

      

    TableName -> (string)

      

      The DynamoDB table with which the stream is associated.

      

      

    StreamLabel -> (string)

      

      A timestamp, in ISO 8601 format, for this stream.

       

      Note that *LatestStreamLabel* is not a unique identifier for the stream, because it is possible that a stream from another table might have the same timestamp. However, the combination of the following three elements is guaranteed to be unique:

       

       
      * the AWS customer ID.
       
      * the table name
       
      * the *StreamLabel* 
       

      

      

    

  

LastEvaluatedStreamArn -> (string)

  

  The stream ARN of the item where the operation stopped, inclusive of the previous result set. Use this value to start a new operation, excluding this value in the new request.

   

  If ``LastEvaluatedStreamArn`` is empty, then the "last page" of results has been processed and there is no more data to be retrieved.

   

  If ``LastEvaluatedStreamArn`` is not empty, it does not necessarily mean that there is more data in the result set. The only way to know when you have reached the end of the result set is when ``LastEvaluatedStreamArn`` is empty.

  

  

