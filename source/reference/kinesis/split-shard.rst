[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis split-shard:


***********
split-shard
***********



===========
Description
===========



Splits a shard into two new shards in the Amazon Kinesis stream to increase the stream's capacity to ingest and transport data. ``split-shard`` is called when there is a need to increase the overall capacity of a stream because of an expected increase in the volume of data records being ingested. 

 

You can also use ``split-shard`` when a shard appears to be approaching its maximum utilization; for example, the producers sending data into the specific shard are suddenly sending more than previously anticipated. You can also call ``split-shard`` to increase stream capacity, so that more Amazon Kinesis applications can simultaneously read data from the stream for real-time processing. 

 

You must specify the shard to be split and the new hash key, which is the position in the shard where the shard gets split in two. In many cases, the new hash key might simply be the average of the beginning and ending hash key, but it can be any hash key value in the range being mapped into the shard. For more information about splitting shards, see `Split a Shard <http://docs.aws.amazon.com/kinesis/latest/dev/kinesis-using-sdk-java-resharding-split.html>`_ in the *Amazon Kinesis Streams Developer Guide* .

 

You can use  describe-stream to determine the shard ID and hash key values for the ``ShardToSplit`` and ``NewStartingHashKey`` parameters that are specified in the ``split-shard`` request.

 

 ``split-shard`` is an asynchronous operation. Upon receiving a ``split-shard`` request, Amazon Kinesis immediately returns a response and sets the stream status to ``UPDATING`` . After the operation is completed, Amazon Kinesis sets the stream status to ``ACTIVE`` . Read and write operations continue to work while the stream is in the ``UPDATING`` state. 

 

You can use ``describe-stream`` to check the status of the stream, which is returned in ``StreamStatus`` . If the stream is in the ``ACTIVE`` state, you can call ``split-shard`` . If a stream is in ``CREATING`` or ``UPDATING`` or ``DELETING`` states, ``describe-stream`` returns a ``ResourceInUseException`` .

 

If the specified stream does not exist, ``describe-stream`` returns a ``ResourceNotFoundException`` . If you try to create more shards than are authorized for your account, you receive a ``LimitExceededException`` . 

 

For the default shard limit for an AWS account, see `Streams Limits <http://docs.aws.amazon.com/kinesis/latest/dev/service-sizes-and-limits.html>`_ in the *Amazon Kinesis Streams Developer Guide* . If you need to increase this limit, `contact AWS Support <http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html>`_ .

 

If you try to operate on too many streams simultaneously using  create-stream ,  delete-stream ,  merge-shards , and/or  split-shard , you receive a ``LimitExceededException`` . 

 

 ``split-shard`` has limit of 5 transactions per second per account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/SplitShard>`_


========
Synopsis
========

::

    split-shard
  --stream-name <value>
  --shard-to-split <value>
  --new-starting-hash-key <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream for the shard split.

  

``--shard-to-split`` (string)


  The shard ID of the shard to split.

  

``--new-starting-hash-key`` (string)


  A hash key value for the starting hash key of one of the child shards created by the split. The hash key range for a given shard constitutes a set of ordered contiguous positive integers. The value for ``NewStartingHashKey`` must be in the range of hash keys being mapped into the shard. The ``NewStartingHashKey`` hash key value and all higher hash key values in hash key range are distributed to one of the child shards. All the lower hash key values in the range are distributed to the other child shard.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None