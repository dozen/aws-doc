[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis enable-enhanced-monitoring:


**************************
enable-enhanced-monitoring
**************************



===========
Description
===========



Enables enhanced Amazon Kinesis stream monitoring for shard-level metrics.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/EnableEnhancedMonitoring>`_


========
Synopsis
========

::

    enable-enhanced-monitoring
  --stream-name <value>
  --shard-level-metrics <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream for which to enable enhanced monitoring.

  

``--shard-level-metrics`` (list)


  List of shard-level metrics to enable.

   

  The following are the valid shard-level metrics. The value "``ALL`` " enables every metric.

   

   
  * ``IncomingBytes``   
   
  * ``IncomingRecords``   
   
  * ``OutgoingBytes``   
   
  * ``OutgoingRecords``   
   
  * ``WriteProvisionedThroughputExceeded``   
   
  * ``ReadProvisionedThroughputExceeded``   
   
  * ``IteratorAgeMilliseconds``   
   
  * ``ALL``   
   

   

  For more information, see `Monitoring the Amazon Kinesis Streams Service with Amazon CloudWatch <http://docs.aws.amazon.com/kinesis/latest/dev/monitoring-with-cloudwatch.html>`_ in the *Amazon Kinesis Streams Developer Guide* .

  



Syntax::

  "string" "string" ...

  Where valid values are:
    IncomingBytes
    IncomingRecords
    OutgoingBytes
    OutgoingRecords
    WriteProvisionedThroughputExceeded
    ReadProvisionedThroughputExceeded
    IteratorAgeMilliseconds
    ALL





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StreamName -> (string)

  

  The name of the Amazon Kinesis stream.

  

  

CurrentShardLevelMetrics -> (list)

  

  Represents the current state of the metrics that are in the enhanced state before the operation.

  

  (string)

    

    

  

DesiredShardLevelMetrics -> (list)

  

  Represents the list of all the metrics that would be in the enhanced state after the operation.

  

  (string)

    

    

  

