[ :ref:`aws <cli:aws>` . :ref:`xray <cli:aws xray>` ]

.. _cli:aws xray put-trace-segments:


******************
put-trace-segments
******************



===========
Description
===========



Uploads segment documents to AWS X-Ray. The X-Ray SDK generates segment documents and sends them to the X-Ray daemon, which uploads them in batches. A segment document can be a completed segment, an in-progress segment, or an array of subsegments.

 

Segments must include the following fields. For the full segment document schema, see `AWS X-Ray Segment Documents <http://docs.aws.amazon.com/xray/latest/devguide/xray-api-segmentdocuments.html>`_ in the *AWS X-Ray Developer Guide* .

 

 **Required Segment Document Fields**  

 

 
* ``name`` - The name of the service that handled the request. 
 
* ``id`` - A 64-bit identifier for the segment, unique among segments in the same trace, in 16 hexadecimal digits. 
 
* ``trace_id`` - A unique identifier that connects all segments and subsegments originating from a single client request. 
 
* ``start_time`` - Time the segment or subsegment was created, in floating point seconds in epoch time, accurate to milliseconds. For example, ``1480615200.010`` or ``1.480615200010E9`` . 
 
* ``end_time`` - Time the segment or subsegment was closed. For example, ``1480615200.090`` or ``1.480615200090E9`` . Specify either an ``end_time`` or ``in_progress`` . 
 
* ``in_progress`` - Set to ``true`` instead of specifying an ``end_time`` to record that a segment has been started, but is not complete. Send an in progress segment when your application receives a request that will take a long time to serve, to trace the fact that the request was received. When the response is sent, send the complete segment to overwrite the in-progress segment. 
 

 

A ``trace_id`` consists of three numbers separated by hyphens. For example, 1-58406520-a006649127e371903a2de979. This includes:

 

 **Trace ID Format**  

 

 
* The version number, i.e. ``1`` . 
 
* The time of the original request, in Unix epoch time, in 8 hexadecimal digits. For example, 10:00AM December 2nd, 2016 PST in epoch time is ``1480615200`` seconds, or ``58406520`` in hexadecimal. 
 
* A 96-bit identifier for the trace, globally unique, in 24 hexadecimal digits. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/xray-2016-04-12/PutTraceSegments>`_


========
Synopsis
========

::

    put-trace-segments
  --trace-segment-documents <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--trace-segment-documents`` (list)


  A string containing a JSON document defining one or more segments or subsegments.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

UnprocessedTraceSegments -> (list)

  

  Segments that failed processing.

  

  (structure)

    

    Information about a segment that failed processing.

    

    Id -> (string)

      

      The segment's ID.

      

      

    ErrorCode -> (string)

      

      The error that caused processing to fail.

      

      

    Message -> (string)

      

      The error message.

      

      

    

  

