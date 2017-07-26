[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis describe-limits:


***************
describe-limits
***************



===========
Description
===========



Describes the shard limits and usage for the account.

 

If you update your account limits, the old limits might be returned for a few minutes.

 

This operation has a limit of 1 transaction per second per account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/DescribeLimits>`_


========
Synopsis
========

::

    describe-limits
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ShardLimit -> (integer)

  

  The maximum number of shards.

  

  

OpenShardCount -> (integer)

  

  The number of open shards.

  

  

