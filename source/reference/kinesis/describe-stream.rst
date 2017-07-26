[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis describe-stream:


***************
describe-stream
***************



===========
Description
===========



Describes the specified stream.

 

The information about the stream includes its current status, its Amazon Resource Name (ARN), and an array of shard objects. For each shard object, there is information about the hash key and sequence number ranges that the shard spans, and the IDs of any earlier shards that played in a role in creating the shard. A sequence number is the identifier associated with every record ingested in the Amazon Kinesis stream. The sequence number is assigned when a record is put into the stream.

 

You can limit the number of returned shards using the ``Limit`` parameter. The number of shards in a stream may be too large to return from a single call to ``describe-stream`` . You can detect this by using the ``HasMoreShards`` flag in the returned output. ``HasMoreShards`` is set to ``true`` when there is more data available. 

 

``describe-stream`` is a paginated operation. If there are more shards available, you can request them using the shard ID of the last shard returned. Specify this ID in the ``ExclusiveStartShardId`` parameter in a subsequent request to ``describe-stream`` . 

 

 describe-stream has a limit of 10 transactions per second per account.



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
  [--generate-cli-skeleton]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

StreamDescription -> (structure)

  

  The current status of the stream, the stream ARN, an array of shard objects that comprise the stream, and states whether there are more shards available.

  

  StreamName -> (string)

    

    The name of the stream being described.

    

    

  StreamARN -> (string)

    

    The Amazon Resource Name (ARN) for the stream being described.

    

    

  StreamStatus -> (string)

    

    The current status of the stream being described.

     

    The stream status is one of the following states:

     

     
    * ``CREATING`` - The stream is being created. Amazon Kinesis immediately returns and sets ``StreamStatus`` to ``CREATING`` .
     
    * ``DELETING`` - The stream is being deleted. The specified stream is in the ``DELETING`` state until Amazon Kinesis completes the deletion.
     
    * ``ACTIVE`` - The stream exists and is ready for read and write operations or deletion. You should perform read and write operations only on an ``ACTIVE`` stream.
     
    * ``UPDATING`` - Shards in the stream are being merged or split. Read and write operations continue to work while the stream is in the ``UPDATING`` state.
     

    

    

  Shards -> (list)

    

    The shards that comprise the stream.

    

    (structure)

      

      A uniquely identified group of data records in an Amazon Kinesis stream.

      

      ShardId -> (string)

        

        The unique identifier of the shard within the Amazon Kinesis stream.

        

        

      ParentShardId -> (string)

        

        The shard Id of the shard's parent.

        

        

      AdjacentParentShardId -> (string)

        

        The shard Id of the shard adjacent to the shard's parent.

        

        

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

    

    

  

