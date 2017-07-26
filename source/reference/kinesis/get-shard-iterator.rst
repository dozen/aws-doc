[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis get-shard-iterator:


******************
get-shard-iterator
******************



===========
Description
===========



Gets an Amazon Kinesis shard iterator. A shard iterator expires five minutes after it is returned to the requester.

 

A shard iterator specifies the shard position from which to start reading data records sequentially. The position is specified using the sequence number of a data record in a shard. A sequence number is the identifier associated with every record ingested in the stream, and is assigned when a record is put into the stream. Each stream has one or more shards.

 

You must specify the shard iterator type. For example, you can set the ``shard-iterator-type`` parameter to read exactly from the position denoted by a specific sequence number by using the ``AT_SEQUENCE_NUMBER`` shard iterator type, or right after the sequence number by using the ``AFTER_SEQUENCE_NUMBER`` shard iterator type, using sequence numbers returned by earlier calls to  put-record ,  put-records ,  get-records , or  describe-stream . In the request, you can specify the shard iterator type ``AT_TIMESTAMP`` to read records from an arbitrary point in time, ``TRIM_HORIZON`` to cause ``ShardIterator`` to point to the last untrimmed record in the shard in the system (the oldest data record in the shard), or ``LATEST`` so that you always read the most recent data in the shard. 

 

When you read repeatedly from a stream, use a  get-shard-iterator request to get the first shard iterator for use in your first  get-records request and for subsequent reads use the shard iterator returned by the  get-records request in ``NextShardIterator`` . A new shard iterator is returned by every  get-records request in ``NextShardIterator`` , which you use in the ``ShardIterator`` parameter of the next  get-records request. 

 

If a  get-shard-iterator request is made too often, you receive a ``ProvisionedThroughputExceededException`` . For more information about throughput limits, see  get-records , and `Streams Limits <http://docs.aws.amazon.com/kinesis/latest/dev/service-sizes-and-limits.html>`_ in the *Amazon Kinesis Streams Developer Guide* .

 

If the shard is closed,  get-shard-iterator returns a valid iterator for the last sequence number of the shard. Note that a shard can be closed as a result of using  split-shard or  merge-shards .

 

  get-shard-iterator has a limit of 5 transactions per second per account per open shard.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/GetShardIterator>`_


========
Synopsis
========

::

    get-shard-iterator
  --stream-name <value>
  --shard-id <value>
  --shard-iterator-type <value>
  [--starting-sequence-number <value>]
  [--timestamp <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-name`` (string)


  The name of the Amazon Kinesis stream.

  

``--shard-id`` (string)


  The shard ID of the Amazon Kinesis shard to get the iterator for.

  

``--shard-iterator-type`` (string)


  Determines how the shard iterator is used to start reading data records from the shard.

   

  The following are the valid Amazon Kinesis shard iterator types:

   

   
  * AT_SEQUENCE_NUMBER - Start reading from the position denoted by a specific sequence number, provided in the value ``StartingSequenceNumber`` . 
   
  * AFTER_SEQUENCE_NUMBER - Start reading right after the position denoted by a specific sequence number, provided in the value ``StartingSequenceNumber`` . 
   
  * AT_TIMESTAMP - Start reading from the position denoted by a specific timestamp, provided in the value ``timestamp`` . 
   
  * TRIM_HORIZON - Start reading at the last untrimmed record in the shard in the system, which is the oldest data record in the shard. 
   
  * LATEST - Start reading just after the most recent record in the shard, so that you always read the most recent data in the shard. 
   

  

  Possible values:

  
  *   ``AT_SEQUENCE_NUMBER``

  
  *   ``AFTER_SEQUENCE_NUMBER``

  
  *   ``TRIM_HORIZON``

  
  *   ``LATEST``

  
  *   ``AT_TIMESTAMP``

  

  

``--starting-sequence-number`` (string)


  The sequence number of the data record in the shard from which to start reading. Used with shard iterator type AT_SEQUENCE_NUMBER and AFTER_SEQUENCE_NUMBER.

  

``--timestamp`` (timestamp)


  The timestamp of the data record from which to start reading. Used with shard iterator type AT_TIMESTAMP. A timestamp is the Unix epoch date with precision in milliseconds. For example, ``2016-04-04T19:58:46.480-00:00`` or ``1459799926.480`` . If a record with this exact timestamp does not exist, the iterator returned is for the next (later) record. If the timestamp is older than the current trim horizon, the iterator returned is for the oldest untrimmed data record (TRIM_HORIZON).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ShardIterator -> (string)

  

  The position in the shard from which to start reading data records sequentially. A shard iterator specifies this position using the sequence number of a data record in a shard.

  

  

