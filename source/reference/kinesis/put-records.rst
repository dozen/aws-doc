[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis put-records:


***********
put-records
***********



===========
Description
===========



Writes multiple data records into an Amazon Kinesis stream in a single call (also referred to as a ``put-records`` request). Use this operation to send data into the stream for data ingestion and processing. 

 

Each ``put-records`` request can support up to 500 records. Each record in the request can be as large as 1 MB, up to a limit of 5 MB for the entire request, including partition keys. Each shard can support writes up to 1,000 records per second, up to a maximum data write total of 1 MB per second.

 

You must specify the name of the stream that captures, stores, and transports the data; and an array of request ``Records`` , with each record in the array requiring a partition key and data blob. The record size limit applies to the total size of the partition key and data blob.

 

The data blob can be any type of data; for example, a segment from a log file, geographic/location data, website clickstream data, and so on.

 

The partition key is used by Amazon Kinesis as input to a hash function that maps the partition key and associated data to a specific shard. An MD5 hash function is used to map partition keys to 128-bit integer values and to map associated data records to shards. As a result of this hashing mechanism, all data records with the same partition key map to the same shard within the stream. For more information, see `Adding Data to a Stream <http://docs.aws.amazon.com/kinesis/latest/dev/developing-producers-with-sdk.html#kinesis-using-sdk-java-add-data-to-stream>`_ in the *Amazon Kinesis Streams Developer Guide* .

 

Each record in the ``Records`` array may include an optional parameter, ``ExplicitHashKey`` , which overrides the partition key to shard mapping. This parameter allows a data producer to determine explicitly the shard where the record is stored. For more information, see `Adding Multiple Records with put-records <http://docs.aws.amazon.com/kinesis/latest/dev/developing-producers-with-sdk.html#kinesis-using-sdk-java-putrecords>`_ in the *Amazon Kinesis Streams Developer Guide* .

 

The ``put-records`` response includes an array of response ``Records`` . Each record in the response array directly correlates with a record in the request array using natural ordering, from the top to the bottom of the request and response. The response ``Records`` array always includes the same number of records as the request array.

 

The response ``Records`` array includes both successfully and unsuccessfully processed records. Amazon Kinesis attempts to process all records in each ``put-records`` request. A single record failure does not stop the processing of subsequent records.

 

A successfully-processed record includes ``ShardId`` and ``SequenceNumber`` values. The ``ShardId`` parameter identifies the shard in the stream where the record is stored. The ``SequenceNumber`` parameter is an identifier assigned to the put record, unique to all records in the stream.

 

An unsuccessfully-processed record includes ``ErrorCode`` and ``ErrorMessage`` values. ``ErrorCode`` reflects the type of error and can be one of the following values: ``ProvisionedThroughputExceededException`` or ``InternalFailure`` . ``ErrorMessage`` provides more detailed information about the ``ProvisionedThroughputExceededException`` exception including the account ID, stream name, and shard ID of the record that was throttled. For more information about partially successful responses, see `Adding Multiple Records with put-records <http://docs.aws.amazon.com/kinesis/latest/dev/kinesis-using-sdk-java-add-data-to-stream.html#kinesis-using-sdk-java-putrecords>`_ in the *Amazon Kinesis Streams Developer Guide* .

 

By default, data records are accessible for 24 hours from the time that they are added to a stream. You can use  increase-stream-retention-period or  decrease-stream-retention-period to modify this retention period.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/PutRecords>`_


========
Synopsis
========

::

    put-records
  --records <value>
  --stream-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--records`` (list)


  The records associated with the request.

  



Shorthand Syntax::

    Data=blob,ExplicitHashKey=string,PartitionKey=string ...




JSON Syntax::

  [
    {
      "Data": blob,
      "ExplicitHashKey": "string",
      "PartitionKey": "string"
    }
    ...
  ]



``--stream-name`` (string)


  The stream name associated with the request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FailedRecordCount -> (integer)

  

  The number of unsuccessfully processed records in a ``put-records`` request.

  

  

Records -> (list)

  

  An array of successfully and unsuccessfully processed record results, correlated with the request by natural ordering. A record that is successfully added to a stream includes ``SequenceNumber`` and ``ShardId`` in the result. A record that fails to be added to a stream includes ``ErrorCode`` and ``ErrorMessage`` in the result.

  

  (structure)

    

    Represents the result of an individual record from a ``put-records`` request. A record that is successfully added to a stream includes ``SequenceNumber`` and ``ShardId`` in the result. A record that fails to be added to the stream includes ``ErrorCode`` and ``ErrorMessage`` in the result.

    

    SequenceNumber -> (string)

      

      The sequence number for an individual record result.

      

      

    ShardId -> (string)

      

      The shard ID for an individual record result.

      

      

    ErrorCode -> (string)

      

      The error code for an individual record result. ``ErrorCodes`` can be either ``ProvisionedThroughputExceededException`` or ``InternalFailure`` .

      

      

    ErrorMessage -> (string)

      

      The error message for an individual record result. An ``ErrorCode`` value of ``ProvisionedThroughputExceededException`` has an error message that includes the account ID, stream name, and shard ID. An ``ErrorCode`` value of ``InternalFailure`` has the error message ``"Internal Service Failure"`` .

      

      

    

  

EncryptionType -> (string)

  

  The encryption type used on the records. This parameter can be one of the following values:

   

   
  * ``NONE`` : Do not encrypt the records. 
   
  * ``KMS`` : Use server-side encryption on the records using a customer-managed KMS key. 
   

  

  

