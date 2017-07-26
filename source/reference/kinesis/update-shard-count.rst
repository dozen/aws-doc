[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis update-shard-count:


******************
update-shard-count
******************



===========
Description
===========



Updates the shard count of the specified stream to the specified number of shards.

 

Updating the shard count is an asynchronous operation. Upon receiving the request, Amazon Kinesis returns immediately and sets the status of the stream to ``UPDATING`` . After the update is complete, Amazon Kinesis sets the status of the stream back to ``ACTIVE`` . Depending on the size of the stream, the scaling action could take a few minutes to complete. You can continue to read and write data to your stream while its status is ``UPDATING`` .

 

To update the shard count, Amazon Kinesis performs splits or merges on individual shards. This can cause short-lived shards to be created, in addition to the final shards. We recommend that you double or halve the shard count, as this results in the fewest number of splits or merges.

 

This operation has the following limits, which are per region per account unless otherwise noted:

 

 
* scale more than twice per rolling 24 hour period 
 
* scale up above double your current shard count 
 
* scale down below half your current shard count 
 
* scale up above 200 shards in a stream 
 
* scale a stream with more than 200 shards down unless the result is less than 200 shards 
 
* scale up above the shard limits for your account 
 
* 
 

 

For the default limits for an AWS account, see `Streams Limits <http://docs.aws.amazon.com/kinesis/latest/dev/service-sizes-and-limits.html>`_ in the *Amazon Kinesis Streams Developer Guide* . If you need to increase a limit, `contact AWS Support <http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/UpdateShardCount>`_


========
Synopsis
========

::

    update-shard-count
  --stream-name <value>
  --target-shard-count <value>
  --scaling-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream.

  

``--target-shard-count`` (integer)


  The new number of shards.

  

``--scaling-type`` (string)


  The scaling type. Uniform scaling creates shards of equal size.

  

  Possible values:

  
  *   ``UNIFORM_SCALING``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StreamName -> (string)

  

  The name of the stream.

  

  

CurrentShardCount -> (integer)

  

  The current number of shards.

  

  

TargetShardCount -> (integer)

  

  The updated number of shards.

  

  

