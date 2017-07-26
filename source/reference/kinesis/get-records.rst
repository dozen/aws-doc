[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis get-records:


***********
get-records
***********



===========
Description
===========



Gets data records from an Amazon Kinesis stream's shard.

 

Specify a shard iterator using the ``shard-iterator`` parameter. The shard iterator specifies the position in the shard from which you want to start reading data records sequentially. If there are no records available in the portion of the shard that the iterator points to,  get-records returns an empty list. Note that it might take multiple calls to get to a portion of the shard that contains records.

 

You can scale by provisioning multiple shards per stream while considering service limits (for more information, see `Streams Limits <http://docs.aws.amazon.com/kinesis/latest/dev/service-sizes-and-limits.html>`_ in the *Amazon Kinesis Streams Developer Guide* ). Your application should have one thread per shard, each reading continuously from its stream. To read from a stream continually, call  get-records in a loop. Use  get-shard-iterator to get the shard iterator to specify in the first  get-records call.  get-records returns a new shard iterator in ``NextShardIterator`` . Specify the shard iterator returned in ``NextShardIterator`` in subsequent calls to  get-records . Note that if the shard has been closed, the shard iterator can't return more data and  get-records returns ``null`` in ``NextShardIterator`` . You can terminate the loop when the shard is closed, or when the shard iterator reaches the record with the sequence number or other attribute that marks it as the last record to process.

 

Each data record can be up to 1 MB in size, and each shard can read up to 2 MB per second. You can ensure that your calls don't exceed the maximum supported size or throughput by using the ``Limit`` parameter to specify the maximum number of records that  get-records can return. Consider your average record size when determining this limit.

 

The size of the data returned by  get-records varies depending on the utilization of the shard. The maximum size of data that  get-records can return is 10 MB. If a call returns this amount of data, subsequent calls made within the next 5 seconds throw ``ProvisionedThroughputExceededException`` . If there is insufficient provisioned throughput on the shard, subsequent calls made within the next 1 second throw ``ProvisionedThroughputExceededException`` . Note that  get-records won't return any data when it throws an exception. For this reason, we recommend that you wait one second between calls to  get-records ; however, it's possible that the application will get exceptions for longer than 1 second.

 

To detect whether the application is falling behind in processing, you can use the ``MillisBehindLatest`` response attribute. You can also monitor the stream using CloudWatch metrics and other mechanisms (see `Monitoring <http://docs.aws.amazon.com/kinesis/latest/dev/monitoring.html>`_ in the *Amazon Kinesis Streams Developer Guide* ).

 

Each Amazon Kinesis record includes a value, ``ApproximateArrivalTimestamp`` , that is set when a stream successfully receives and stores a record. This is commonly referred to as a server-side timestamp, whereas a client-side timestamp is set when a data producer creates or sends the record to a stream (a data producer is any data source putting data records into a stream, for example with  put-records ). The timestamp has millisecond precision. There are no guarantees about the timestamp accuracy, or that the timestamp is always increasing. For example, records in a shard or across a stream might have timestamps that are out of order.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/GetRecords>`_


========
Synopsis
========

::

    get-records
  --shard-iterator <value>
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--shard-iterator`` (string)


  The position in the shard from which you want to start sequentially reading data records. A shard iterator specifies this position using the sequence number of a data record in the shard.

  

``--limit`` (integer)


  The maximum number of records to return. Specify a value of up to 10,000. If you specify a value that is greater than 10,000,  get-records throws ``InvalidArgumentException`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Records -> (list)

  

  The data records retrieved from the shard.

  

  (structure)

    

    The unit of data of the Amazon Kinesis stream, which is composed of a sequence number, a partition key, and a data blob.

    

    SequenceNumber -> (string)

      

      The unique identifier of the record within its shard.

      

      

    ApproximateArrivalTimestamp -> (timestamp)

      

      The approximate time that the record was inserted into the stream.

      

      

    Data -> (blob)

      

      The data blob. The data in the blob is both opaque and immutable to the Amazon Kinesis service, which does not inspect, interpret, or change the data in the blob in any way. When the data blob (the payload before base64-encoding) is added to the partition key size, the total size must not exceed the maximum record size (1 MB).

      

      

    PartitionKey -> (string)

      

      Identifies which shard in the stream the data record is assigned to.

      

      

    EncryptionType -> (string)

      

      The encryption type used on the record. This parameter can be one of the following values:

       

       
      * ``NONE`` : Do not encrypt the records in the stream. 
       
      * ``KMS`` : Use server-side encryption on the records in the stream using a customer-managed KMS key. 
       

      

      

    

  

NextShardIterator -> (string)

  

  The next position in the shard from which to start sequentially reading data records. If set to ``null`` , the shard has been closed and the requested iterator will not return any more data. 

  

  

MillisBehindLatest -> (long)

  

  The number of milliseconds the  get-records response is from the tip of the stream, indicating how far behind current time the consumer is. A value of zero indicates record processing is caught up, and there are no new records to process at this moment.

  

  

