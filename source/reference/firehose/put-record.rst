[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose put-record:


**********
put-record
**********



===========
Description
===========



Writes a single data record into an Amazon Kinesis Firehose delivery stream. To write multiple data records into a delivery stream, use  put-record-batch . Applications using these operations are referred to as producers.

 

By default, each delivery stream can take in up to 2,000 transactions per second, 5,000 records per second, or 5 MB per second. Note that if you use  put-record and  put-record-batch , the limits are an aggregate across these two operations for each delivery stream. For more information about limits and how to request an increase, see `Amazon Kinesis Firehose Limits <http://docs.aws.amazon.com/firehose/latest/dev/limits.html>`_ . 

 

You must specify the name of the delivery stream and the data record when using  put-record . The data record consists of a data blob that can be up to 1,000 KB in size, and any kind of data, for example, a segment from a log file, geographic location data, web site clickstream data, etc.

 

Firehose buffers records before delivering them to the destination. To disambiguate the data blobs at the destination, a common solution is to use delimiters in the data, such as a newline (``\n`` ) or some other character unique within the data. This allows the consumer application(s) to parse individual data items when reading the data from the destination.

 

The  put-record operation returns a **RecordId** , which is a unique string assigned to each record. Producer applications can use this ID for purposes such as auditability and investigation.

 

If the  put-record operation throws a **ServiceUnavailableException** , back off and retry. If the exception persists, it is possible that the throughput limits have been exceeded for the delivery stream. 

 

Data records sent to Firehose are stored for 24 hours from the time they are added to a delivery stream as it attempts to send the records to the destination. If the destination is unreachable for more than 24 hours, the data is no longer available.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/firehose-2015-08-04/PutRecord>`_


========
Synopsis
========

::

    put-record
  --delivery-stream-name <value>
  --record <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--delivery-stream-name`` (string)


  The name of the delivery stream.

  

``--record`` (structure)


  The record.

  



Shorthand Syntax::

    Data=blob




JSON Syntax::

  {
    "Data": blob
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

RecordId -> (string)

  

  The ID of the record.

  

  

