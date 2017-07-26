[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis describe-stream:


***************
describe-stream
***************



===========
Description
===========



Describes the specified Amazon Kinesis stream.

 

The information returned includes the stream name, Amazon Resource Name (ARN), creation time, enhanced metric configuration, and shard map. The shard map is an array of shard objects. For each shard object, there is the hash key and sequence number ranges that the shard spans, and the IDs of any earlier shards that played in a role in creating the shard. Every record ingested in the stream is identified by a sequence number, which is assigned when the record is put into the stream.

 

You can limit the number of shards returned by each call. For more information, see `Retrieving Shards from a Stream <http://docs.aws.amazon.com/kinesis/latest/dev/kinesis-using-sdk-java-retrieve-shards.html>`_ in the *Amazon Kinesis Streams Developer Guide* .

 

There are no guarantees about the chronological order shards returned. To process shards in chronological order, use the ID of the parent shard to track the lineage to the oldest shard.

 

This operation has a limit of 10 transactions per second per account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/DescribeStream>`_


``describe-stream`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``StreamDescription.Shards``


========
Synopsis
========

::

    describe-stream
  --stream-name <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StreamDescription -> (structure)

  

  The current status of the stream, the stream ARN, an array of shard objects that comprise the stream, and whether there are more shards available.

  

  StreamName -> (string)

    

    The name of the stream being described.

    

    

  StreamARN -> (string)

    

    The Amazon Resource Name (ARN) for the stream being described.

    

    

  StreamStatus -> (string)

    

    The current status of the stream being described. The stream status is one of the following states:

     

     
    * ``CREATING`` - The stream is being created. Amazon Kinesis immediately returns and sets ``StreamStatus`` to ``CREATING`` . 
     
    * ``DELETING`` - The stream is being deleted. The specified stream is in the ``DELETING`` state until Amazon Kinesis completes the deletion. 
     
    * ``ACTIVE`` - The stream exists and is ready for read and write operations or deletion. You should perform read and write operations only on an ``ACTIVE`` stream. 
     
    * ``UPDATING`` - Shards in the stream are being merged or split. Read and write operations continue to work while the stream is in the ``UPDATING`` state. 
     

    

    

  Shards -> (list)

    

    The shards that comprise the stream.

    

    (structure)

      

      A uniquely identified group of data records in an Amazon Kinesis stream.

      

      ShardId -> (string)

        

        The unique identifier of the shard within the stream.

        

        

      ParentShardId -> (string)

        

        The shard ID of the shard's parent.

        

        

      AdjacentParentShardId -> (string)

        

        The shard ID of the shard adjacent to the shard's parent.

        

        

      HashKeyRange -> (structure)

        

        The range of possible hash key values for the shard, which is a set of ordered contiguous positive integers.

        

        StartingHashKey -> (string)

          

          The starting hash key of the hash key range.

          

          

        EndingHashKey -> (string)

          

          The ending hash key of the hash key range.

          

          

        

      SequenceNumberRange -> (structure)

        

        The range of possible sequence numbers for the shard.

        

        StartingSequenceNumber -> (string)

          

          The starting sequence number for the range.

          

          

        EndingSequenceNumber -> (string)

          

          The ending sequence number for the range. Shards that are in the OPEN state have an ending sequence number of ``null`` .

          

          

        

      

    

  HasMoreShards -> (boolean)

    

    If set to ``true`` , more shards in the stream are available to describe.

    

    

  RetentionPeriodHours -> (integer)

    

    The current retention period, in hours.

    

    

  StreamCreationTimestamp -> (timestamp)

    

    The approximate time that the stream was created.

    

    

  EnhancedMonitoring -> (list)

    

    Represents the current enhanced monitoring settings of the stream.

    

    (structure)

      

      Represents enhanced metrics types.

      

      ShardLevelMetrics -> (list)

        

        List of shard-level metrics.

         

        The following are the valid shard-level metrics. The value "``ALL`` " enhances every metric.

         

         
        * ``IncomingBytes``   
         
        * ``IncomingRecords``   
         
        * ``OutgoingBytes``   
         
        * ``OutgoingRecords``   
         
        * ``WriteProvisionedThroughputExceeded``   
         
        * ``ReadProvisionedThroughputExceeded``   
         
        * ``IteratorAgeMilliseconds``   
         
        * ``ALL``   
         

         

        For more information, see `Monitoring the Amazon Kinesis Streams Service with Amazon CloudWatch <http://docs.aws.amazon.com/kinesis/latest/dev/monitoring-with-cloudwatch.html>`_ in the *Amazon Kinesis Streams Developer Guide* .

        

        (string)

          

          

        

      

    

  EncryptionType -> (string)

    

    The server-side encryption type used on the stream. This parameter can be one of the following values:

     

     
    * ``NONE`` : Do not encrypt the records in the stream. 
     
    * ``KMS`` : Use server-side encryption on the records in the stream using a customer-managed KMS key. 
     

    

    

  KeyId -> (string)

    

    The GUID for the customer-managed KMS key used for encryption on the stream.

    

    

  

