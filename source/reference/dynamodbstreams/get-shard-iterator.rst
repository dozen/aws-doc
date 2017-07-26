[ :ref:`aws <cli:aws>` . :ref:`dynamodbstreams <cli:aws dynamodbstreams>` ]

.. _cli:aws dynamodbstreams get-shard-iterator:


******************
get-shard-iterator
******************



===========
Description
===========



Returns a shard iterator. A shard iterator provides information about how to retrieve the stream records from within a shard. Use the shard iterator in a subsequent ``get-records`` request to read the stream records from the shard.

 

.. note::

  

  A shard iterator expires 15 minutes after it is returned to the requester.

  



========
Synopsis
========

::

    get-shard-iterator
  --stream-arn <value>
  --shard-id <value>
  --shard-iterator-type <value>
  [--sequence-number <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stream-arn`` (string)


  The Amazon Resource Name (ARN) for the stream.

  

``--shard-id`` (string)


  The identifier of the shard. The iterator will be returned for this shard ID.

  

``--shard-iterator-type`` (string)


  Determines how the shard iterator is used to start reading stream records from the shard:

   

   
  * ``AT_SEQUENCE_NUMBER`` - Start reading exactly from the position denoted by a specific sequence number. 
   
  * ``AFTER_SEQUENCE_NUMBER`` - Start reading right after the position denoted by a specific sequence number. 
   
  * ``TRIM_HORIZON`` - Start reading at the last (untrimmed) stream record, which is the oldest record in the shard. In DynamoDB Streams, there is a 24 hour limit on data retention. Stream records whose age exceeds this limit are subject to removal (trimming) from the stream. 
   
  * ``LATEST`` - Start reading just after the most recent stream record in the shard, so that you always read the most recent data in the shard. 
   

  

  Possible values:

  
  *   ``TRIM_HORIZON``

  
  *   ``LATEST``

  
  *   ``AT_SEQUENCE_NUMBER``

  
  *   ``AFTER_SEQUENCE_NUMBER``

  

  

``--sequence-number`` (string)


  The sequence number of a stream record in the shard from which to start reading.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ShardIterator -> (string)

  

  The position in the shard from which to start reading stream records sequentially. A shard iterator specifies this position using the sequence number of a stream record in a shard.

  

  

