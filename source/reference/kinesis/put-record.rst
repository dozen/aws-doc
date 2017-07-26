[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis put-record:


**********
put-record
**********



===========
Description
===========



Writes a single data record into an Amazon Kinesis stream. Call ``put-record`` to send data into the stream for real-time ingestion and subsequent processing, one record at a time. Each shard can support writes up to 1,000 records per second, up to a maximum data write total of 1 MB per second.

 

You must specify the name of the stream that captures, stores, and transports the data; a partition key; and the data blob itself.

 

The data blob can be any type of data; for example, a segment from a log file, geographic/location data, website clickstream data, and so on.

 

The partition key is used by Amazon Kinesis to distribute data across shards. Amazon Kinesis segregates the data records that belong to a stream into multiple shards, using the partition key associated with each data record to determine which shard a given data record belongs to.

 

Partition keys are Unicode strings, with a maximum length limit of 256 characters for each key. An MD5 hash function is used to map partition keys to 128-bit integer values and to map associated data records to shards using the hash key ranges of the shards. You can override hashing the partition key to determine the shard by explicitly specifying a hash value using the ``ExplicitHashKey`` parameter. For more information, see `Adding data to a Stream <http://docs.aws.amazon.com/kinesis/latest/dev/developing-producers-with-sdk.html#kinesis-using-sdk-java-add-data-to-stream>`_ in the *Amazon Kinesis Streams Developer Guide* .

 

 ``put-record`` returns the shard ID of where the data record was placed and the sequence number that was assigned to the data record.

 

Sequence numbers increase over time and are specific to a shard within a stream, not across all shards within a stream. To guarantee strictly increasing ordering, write serially to a shard and use the ``SequenceNumberForOrdering`` parameter. For more information, see `Adding data to a Stream <http://docs.aws.amazon.com/kinesis/latest/dev/developing-producers-with-sdk.html#kinesis-using-sdk-java-add-data-to-stream>`_ in the *Amazon Kinesis Streams Developer Guide* .

 

If a ``put-record`` request cannot be processed because of insufficient provisioned throughput on the shard involved in the request, ``put-record`` throws ``ProvisionedThroughputExceededException`` . 

 

By default, data records are accessible for 24 hours from the time that they are added to a stream. You can use  increase-stream-retention-period or  decrease-stream-retention-period to modify this retention period.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/PutRecord>`_


========
Synopsis
========

::

    put-record
  --stream-name <value>
  --data <value>
  --partition-key <value>
  [--explicit-hash-key <value>]
  [--sequence-number-for-ordering <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream to put the data record into.

  

``--data`` (blob)


  The data blob to put into the record, which is base64-encoded when the blob is serialized. When the data blob (the payload before base64-encoding) is added to the partition key size, the total size must not exceed the maximum record size (1 MB).

  

``--partition-key`` (string)


  Determines which shard in the stream the data record is assigned to. Partition keys are Unicode strings with a maximum length limit of 256 characters for each key. Amazon Kinesis uses the partition key as input to a hash function that maps the partition key and associated data to a specific shard. Specifically, an MD5 hash function is used to map partition keys to 128-bit integer values and to map associated data records to shards. As a result of this hashing mechanism, all data records with the same partition key map to the same shard within the stream.

  

``--explicit-hash-key`` (string)


  The hash value used to explicitly determine the shard the data record is assigned to by overriding the partition key hash.

  

``--sequence-number-for-ordering`` (string)


  Guarantees strictly increasing sequence numbers, for puts from the same client and to the same partition key. Usage: set the ``SequenceNumberForOrdering`` of record *n* to the sequence number of record *n-1* (as returned in the result when putting record *n-1* ). If this parameter is not set, records will be coarsely ordered based on arrival time.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ShardId -> (string)

  

  The shard ID of the shard where the data record was placed.

  

  

SequenceNumber -> (string)

  

  The sequence number identifier that was assigned to the put data record. The sequence number for the record is unique across all records in the stream. A sequence number is the identifier associated with every record put into the stream.

  

  

EncryptionType -> (string)

  

  The encryption type to use on the record. This parameter can be one of the following values:

   

   
  * ``NONE`` : Do not encrypt the records in the stream. 
   
  * ``KMS`` : Use server-side encryption on the records in the stream using a customer-managed KMS key. 
   

  

  

