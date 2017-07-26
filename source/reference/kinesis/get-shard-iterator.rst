[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis get-shard-iterator:


******************
get-shard-iterator
******************



===========
Description
===========



Gets a shard iterator. A shard iterator expires five minutes after it is returned to the requester.

 

A shard iterator specifies the position in the shard from which to start reading data records sequentially. A shard iterator specifies this position using the sequence number of a data record in a shard. A sequence number is the identifier associated with every record ingested in the Amazon Kinesis stream. The sequence number is assigned when a record is put into the stream. 

 

You must specify the shard iterator type. For example, you can set the ``shard-iterator-type`` parameter to read exactly from the position denoted by a specific sequence number by using the ``AT_SEQUENCE_NUMBER`` shard iterator type, or right after the sequence number by using the ``AFTER_SEQUENCE_NUMBER`` shard iterator type, using sequence numbers returned by earlier calls to  put-record ,  put-records ,  get-records , or  describe-stream . You can specify the shard iterator type ``TRIM_HORIZON`` in the request to cause ``ShardIterator`` to point to the last untrimmed record in the shard in the system, which is the oldest data record in the shard. Or you can point to just after the most recent record in the shard, by using the shard iterator type ``LATEST`` , so that you always read the most recent data in the shard. 

 

When you repeatedly read from an Amazon Kinesis stream use a  get-shard-iterator request to get the first shard iterator for use in your first  get-records request and then use the shard iterator returned by the  get-records request in ``NextShardIterator`` for subsequent reads. A new shard iterator is returned by every  get-records request in ``NextShardIterator`` , which you use in the ``ShardIterator`` parameter of the next  get-records request. 

 

If a  get-shard-iterator request is made too often, you receive a ``ProvisionedThroughputExceededException`` . For more information about throughput limits, see  get-records .

 

If the shard is closed, the iterator can't return more data, and  get-shard-iterator returns ``null`` for its ``ShardIterator`` . A shard can be closed using  split-shard or  merge-shards .

 

 get-shard-iterator has a limit of 5 transactions per second per account per open shard.



========
Synopsis
========

::

    get-shard-iterator
  --stream-name <value>
  --shard-id <value>
  --shard-iterator-type <value>
  [--starting-sequence-number <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream.

  

``--shard-id`` (string)


  The shard ID of the shard to get the iterator for.

  

``--shard-iterator-type`` (string)


  Determines how the shard iterator is used to start reading data records from the shard.

   

  The following are the valid shard iterator types:

   

   
  * AT_SEQUENCE_NUMBER - Start reading exactly from the position denoted by a specific sequence number.
   
  * AFTER_SEQUENCE_NUMBER - Start reading right after the position denoted by a specific sequence number.
   
  * TRIM_HORIZON - Start reading at the last untrimmed record in the shard in the system, which is the oldest data record in the shard.
   
  * LATEST - Start reading just after the most recent record in the shard, so that you always read the most recent data in the shard.
   

  

  Possible values:

  
  *   ``AT_SEQUENCE_NUMBER``

  
  *   ``AFTER_SEQUENCE_NUMBER``

  
  *   ``TRIM_HORIZON``

  
  *   ``LATEST``

  

  

``--starting-sequence-number`` (string)


  The sequence number of the data record in the shard from which to start reading from.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ShardIterator -> (string)

  

  The position in the shard from which to start reading data records sequentially. A shard iterator specifies this position using the sequence number of a data record in a shard.

  

  

