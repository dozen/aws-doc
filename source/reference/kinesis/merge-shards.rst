[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis merge-shards:


************
merge-shards
************



===========
Description
===========



Merges two adjacent shards in a stream and combines them into a single shard to reduce the stream's capacity to ingest and transport data. Two shards are considered adjacent if the union of the hash key ranges for the two shards form a contiguous set with no gaps. For example, if you have two shards, one with a hash key range of 276...381 and the other with a hash key range of 382...454, then you could merge these two shards into a single shard that would have a hash key range of 276...454. After the merge, the single child shard receives data for all hash key values covered by the two parent shards.

 

``merge-shards`` is called when there is a need to reduce the overall capacity of a stream because of excess capacity that is not being used. You must specify the shard to be merged and the adjacent shard for a stream. For more information about merging shards, see `Merge Two Shards`_ in the *Amazon Kinesis Developer Guide* .

 

If the stream is in the ``ACTIVE`` state, you can call ``merge-shards`` . If a stream is in the ``CREATING`` , ``UPDATING`` , or ``DELETING`` state, ``merge-shards`` returns a ``ResourceInUseException`` . If the specified stream does not exist, ``merge-shards`` returns a ``ResourceNotFoundException`` . 

 

You can use  describe-stream to check the state of the stream, which is returned in ``StreamStatus`` .

 

``merge-shards`` is an asynchronous operation. Upon receiving a ``merge-shards`` request, Amazon Kinesis immediately returns a response and sets the ``StreamStatus`` to ``UPDATING`` . After the operation is completed, Amazon Kinesis sets the ``StreamStatus`` to ``ACTIVE`` . Read and write operations continue to work while the stream is in the ``UPDATING`` state. 

 

You use  describe-stream to determine the shard IDs that are specified in the ``merge-shards`` request. 

 

If you try to operate on too many streams in parallel using  create-stream ,  delete-stream , ``merge-shards`` or  split-shard , you will receive a ``LimitExceededException`` . 

 

``merge-shards`` has limit of 5 transactions per second per account.



========
Synopsis
========

::

    merge-shards
  --stream-name <value>
  --shard-to-merge <value>
  --adjacent-shard-to-merge <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream for the merge.

  

``--shard-to-merge`` (string)


  The shard ID of the shard to combine with the adjacent shard for the merge.

  

``--adjacent-shard-to-merge`` (string)


  The shard ID of the adjacent shard for the merge.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Merge Two Shards: http://docs.aws.amazon.com/kinesis/latest/dev/kinesis-using-sdk-java-resharding-merge.html
