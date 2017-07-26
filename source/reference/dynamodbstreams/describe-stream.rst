[ :ref:`aws <cli:aws>` . :ref:`dynamodbstreams <cli:aws dynamodbstreams>` ]

.. _cli:aws dynamodbstreams describe-stream:


***************
describe-stream
***************



===========
Description
===========



Returns information about a stream, including the current status of the stream, its Amazon Resource Name (ARN), the composition of its shards, and its corresponding DynamoDB table.

 

.. note::

   

  You can call ``describe-stream`` at a maximum rate of 10 times per second.

   

 

Each shard in the stream has a ``SequenceNumberRange`` associated with it. If the ``SequenceNumberRange`` has a ``StartingSequenceNumber`` but no ``EndingSequenceNumber`` , then the shard is still open (able to receive more stream records). If both ``StartingSequenceNumber`` and ``EndingSequenceNumber`` are present, then that shard is closed and can no longer receive more data.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/streams-dynamodb-2012-08-10/DescribeStream>`_


========
Synopsis
========

::

    describe-stream
  --stream-arn <value>
  [--limit <value>]
  [--exclusive-start-shard-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-arn`` (string)


  The Amazon Resource Name (ARN) for the stream.

  

``--limit`` (integer)


  The maximum number of shard objects to return. The upper limit is 100.

  

``--exclusive-start-shard-id`` (string)


  The shard ID of the first item that this operation will evaluate. Use the value that was returned for ``LastEvaluatedShardId`` in the previous operation. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StreamDescription -> (structure)

  

  A complete description of the stream, including its creation date and time, the DynamoDB table associated with the stream, the shard IDs within the stream, and the beginning and ending sequence numbers of stream records within the shards.

  

  StreamArn -> (string)

    

    The Amazon Resource Name (ARN) for the stream.

    

    

  StreamLabel -> (string)

    

    A timestamp, in ISO 8601 format, for this stream.

     

    Note that ``LatestStreamLabel`` is not a unique identifier for the stream, because it is possible that a stream from another table might have the same timestamp. However, the combination of the following three elements is guaranteed to be unique:

     

     
    * the AWS customer ID. 
     
    * the table name 
     
    * the ``StreamLabel``   
     

    

    

  StreamStatus -> (string)

    

    Indicates the current status of the stream:

     

     
    * ``ENABLING`` - Streams is currently being enabled on the DynamoDB table. 
     
    * ``ENABLED`` - the stream is enabled. 
     
    * ``DISABLING`` - Streams is currently being disabled on the DynamoDB table. 
     
    * ``DISABLED`` - the stream is disabled. 
     

    

    

  StreamViewType -> (string)

    

    Indicates the format of the records within this stream:

     

     
    * ``KEYS_ONLY`` - only the key attributes of items that were modified in the DynamoDB table. 
     
    * ``NEW_IMAGE`` - entire items from the table, as they appeared after they were modified. 
     
    * ``OLD_IMAGE`` - entire items from the table, as they appeared before they were modified. 
     
    * ``NEW_AND_OLD_IMAGES`` - both the new and the old images of the items from the table. 
     

    

    

  CreationRequestDateTime -> (timestamp)

    

    The date and time when the request to create this stream was issued.

    

    

  TableName -> (string)

    

    The DynamoDB table with which the stream is associated.

    

    

  KeySchema -> (list)

    

    The key attribute(s) of the stream's DynamoDB table.

    

    (structure)

      

      Represents *a single element* of a key schema. A key schema specifies the attributes that make up the primary key of a table, or the key attributes of an index.

       

      A ``KeySchemaElement`` represents exactly one attribute of the primary key. For example, a simple primary key (partition key) would be represented by one ``KeySchemaElement`` . A composite primary key (partition key and sort key) would require one ``KeySchemaElement`` for the partition key, and another ``KeySchemaElement`` for the sort key.

       

      .. note::

         

        The partition key of an item is also known as its *hash attribute* . The term "hash attribute" derives from DynamoDB's usage of an internal hash function to evenly distribute data items across partitions, based on their partition key values.

         

        The sort key of an item is also known as its *range attribute* . The term "range attribute" derives from the way DynamoDB stores items with the same partition key physically close together, in sorted order by the sort key value.

         

      

      AttributeName -> (string)

        

        The name of a key attribute.

        

        

      KeyType -> (string)

        

        The attribute data, consisting of the data type and the attribute value itself.

        

        

      

    

  Shards -> (list)

    

    The shards that comprise the stream.

    

    (structure)

      

      A uniquely identified group of stream records within a stream.

      

      ShardId -> (string)

        

        The system-generated identifier for this shard.

        

        

      SequenceNumberRange -> (structure)

        

        The range of possible sequence numbers for the shard.

        

        StartingSequenceNumber -> (string)

          

          The first sequence number.

          

          

        EndingSequenceNumber -> (string)

          

          The last sequence number.

          

          

        

      ParentShardId -> (string)

        

        The shard ID of the current shard's parent.

        

        

      

    

  LastEvaluatedShardId -> (string)

    

    The shard ID of the item where the operation stopped, inclusive of the previous result set. Use this value to start a new operation, excluding this value in the new request.

     

    If ``LastEvaluatedShardId`` is empty, then the "last page" of results has been processed and there is currently no more data to be retrieved.

     

    If ``LastEvaluatedShardId`` is not empty, it does not necessarily mean that there is more data in the result set. The only way to know when you have reached the end of the result set is when ``LastEvaluatedShardId`` is empty.

    

    

  

