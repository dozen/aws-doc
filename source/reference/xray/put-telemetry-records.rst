[ :ref:`aws <cli:aws>` . :ref:`xray <cli:aws xray>` ]

.. _cli:aws xray put-telemetry-records:


*********************
put-telemetry-records
*********************



===========
Description
===========



Used by the AWS X-Ray daemon to upload telemetry.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/xray-2016-04-12/PutTelemetryRecords>`_


========
Synopsis
========

::

    put-telemetry-records
  --telemetry-records <value>
  [--ec2-instance-id <value>]
  [--hostname <value>]
  [--resource-arn <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--telemetry-records`` (list)


  

  



Shorthand Syntax::

    Timestamp=timestamp,SegmentsReceivedCount=integer,SegmentsSentCount=integer,SegmentsSpilloverCount=integer,SegmentsRejectedCount=integer,BackendConnectionErrors={TimeoutCount=integer,ConnectionRefusedCount=integer,HTTPCode4XXCount=integer,HTTPCode5XXCount=integer,UnknownHostCount=integer,OtherCount=integer} ...




JSON Syntax::

  [
    {
      "Timestamp": timestamp,
      "SegmentsReceivedCount": integer,
      "SegmentsSentCount": integer,
      "SegmentsSpilloverCount": integer,
      "SegmentsRejectedCount": integer,
      "BackendConnectionErrors": {
        "TimeoutCount": integer,
        "ConnectionRefusedCount": integer,
        "HTTPCode4XXCount": integer,
        "HTTPCode5XXCount": integer,
        "UnknownHostCount": integer,
        "OtherCount": integer
      }
    }
    ...
  ]



``--ec2-instance-id`` (string)


  

  

``--hostname`` (string)


  

  

``--resource-arn`` (string)


  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

