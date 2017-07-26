[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose put-record-batch:


****************
put-record-batch
****************



===========
Description
===========



Writes multiple data records into a delivery stream in a single call, which can achieve higher throughput per producer than when writing single records. To write single data records into a delivery stream, use  put-record . Applications using these operations are referred to as producers.

 

Each  put-record-batch request supports up to 500 records. Each record in the request can be as large as 1,000 KB (before 64-bit encoding), up to a limit of 4 MB for the entire request. By default, each delivery stream can take in up to 2,000 transactions per second, 5,000 records per second, or 5 MB per second. Note that if you use  put-record and  put-record-batch , the limits are an aggregate across these two operations for each delivery stream. For more information about limits and how to request an increase, see `Amazon Kinesis Firehose Limits`_ . 

 

You must specify the name of the delivery stream and the data record when using  put-record . The data record consists of a data blob that can be up to 1,000 KB in size, and any kind of data, for example, a segment from a log file, geographic location data, web site clickstream data, and so on.

 

Amazon Kinesis Firehose buffers records before delivering them to the destination. To disambiguate the data blobs at the destination, a common solution is to use delimiters in the data, such as a newline (``\n`` ) or some other character unique within the data. This allows the consumer application(s) to parse individual data items when reading the data from the destination.

 

The  put-record-batch response includes a count of any failed records, ``FailedPutCount`` , and an array of responses, ``RequestResponses`` . The ``FailedPutCount`` value is a count of records that failed. Each entry in the ``RequestResponses`` array gives additional information of the processed record. Each entry in ``RequestResponses`` directly correlates with a record in the request array using the same ordering, from the top to the bottom of the request and response. ``RequestResponses`` always includes the same number of records as the request array. ``RequestResponses`` both successfully and unsuccessfully processed records. Amazon Kinesis Firehose attempts to process all records in each  put-record-batch request. A single record failure does not stop the processing of subsequent records.

 

A successfully processed record includes a ``RecordId`` value, which is a unique value identified for the record. An unsuccessfully processed record includes ``ErrorCode`` and ``ErrorMessage`` values. ``ErrorCode`` reflects the type of error and is one of the following values: ``ServiceUnavailable`` or ``InternalFailure`` . ``ErrorMessage`` provides more detailed information about the error.

 

If ``FailedPutCount`` is greater than 0 (zero), retry the request. A retry of the entire batch of records is possible; however, we strongly recommend that you inspect the entire response and resend only those records that failed processing. This minimizes duplicate records and also reduces the total bytes sent (and corresponding charges).

 

If the  put-record-batch operation throws a ``ServiceUnavailableException`` , back off and retry. If the exception persists, it is possible that the throughput limits have been exceeded for the delivery stream.

 

Data records sent to Amazon Kinesis Firehose are stored for 24 hours from the time they are added to a delivery stream as it attempts to send the records to the destination. If the destination is unreachable for more than 24 hours, the data is no longer available.



========
Synopsis
========

::

    put-record-batch
  --delivery-stream-name <value>
  --records <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--delivery-stream-name`` (string)


  The name of the delivery stream.

  

``--records`` (list)


  One or more records.

  



Shorthand Syntax::

    --records Data1 Data2 Data3




JSON Syntax::

  [
    {
      "Data": blob
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FailedPutCount -> (integer)

  

  The number of unsuccessfully written records.

  

  

RequestResponses -> (list)

  

  The results for the individual records. The index of each element matches the same index in which records were sent.

  

  (structure)

    

    Contains the result for an individual record from a  put-record-batch request. If the record is successfully added to your delivery stream, it receives a record ID. If the record fails to be added to your delivery stream, the result includes an error code and an error message.

    

    RecordId -> (string)

      

      The ID of the record.

      

      

    ErrorCode -> (string)

      

      The error code for an individual record result.

      

      

    ErrorMessage -> (string)

      

      The error message for an individual record result.

      

      

    

  



.. _Amazon Kinesis Firehose Limits: http://docs.aws.amazon.com/firehose/latest/dev/limits.html
