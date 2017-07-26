[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis create-stream:


*************
create-stream
*************



===========
Description
===========



Creates a Amazon Kinesis stream. A stream captures and transports data records that are continuously emitted from different data sources or *producers* . Scale-out within an Amazon Kinesis stream is explicitly supported by means of shards, which are uniquely identified groups of data records in an Amazon Kinesis stream.

 

You specify and control the number of shards that a stream is composed of. Each shard can support reads up to 5 transactions per second, up to a maximum data read total of 2 MB per second. Each shard can support writes up to 1,000 records per second, up to a maximum data write total of 1 MB per second. You can add shards to a stream if the amount of data input increases and you can remove shards if the amount of data input decreases.

 

The stream name identifies the stream. The name is scoped to the AWS account used by the application. It is also scoped by region. That is, two streams in two different accounts can have the same name, and two streams in the same account, but in two different regions, can have the same name. 

 

``create-stream`` is an asynchronous operation. Upon receiving a ``create-stream`` request, Amazon Kinesis immediately returns and sets the stream status to ``CREATING`` . After the stream is created, Amazon Kinesis sets the stream status to ``ACTIVE`` . You should perform read and write operations only on an ``ACTIVE`` stream. 

 

You receive a ``LimitExceededException`` when making a ``create-stream`` request if you try to do one of the following:

 

 
* Have more than five streams in the ``CREATING`` state at any point in time.
 
* Create more shards than are authorized for your account.
 

 

For the default shard limit for an AWS account, see `Amazon Kinesis Limits`_ . If you need to increase this limit, `contact AWS Support`_ .

 

You can use ``describe-stream`` to check the stream status, which is returned in ``StreamStatus`` .

 

 create-stream has a limit of 5 transactions per second per account.



========
Synopsis
========

::

    create-stream
  --stream-name <value>
  --shard-count <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stream-name`` (string)


  A name to identify the stream. The stream name is scoped to the AWS account used by the application that creates the stream. It is also scoped by region. That is, two streams in two different AWS accounts can have the same name, and two streams in the same AWS account, but in two different regions, can have the same name.

  

``--shard-count`` (integer)


  The number of shards that the stream will use. The throughput of the stream is a function of the number of shards; more shards are required for greater provisioned throughput.

   

  DefaultShardLimit;

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _contact AWS Support: http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html
.. _Amazon Kinesis Limits: http://docs.aws.amazon.com/kinesis/latest/dev/service-sizes-and-limits.html
