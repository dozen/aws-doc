[ :ref:`aws <cli:aws>` . :ref:`xray <cli:aws xray>` ]

.. _cli:aws xray batch-get-traces:


****************
batch-get-traces
****************



===========
Description
===========



Retrieves a list of traces specified by ID. Each trace is a collection of segment documents that originates from a single request. Use ``get-trace-summaries`` to get a list of trace IDs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/xray-2016-04-12/BatchGetTraces>`_


========
Synopsis
========

::

    batch-get-traces
  --trace-ids <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--trace-ids`` (list)


  Specify the trace IDs of requests for which to retrieve segments.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  Pagination token. Not used.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Traces -> (list)

  

  Full traces for the specified requests.

  

  (structure)

    

    A collection of segment documents with matching trace IDs.

    

    Id -> (string)

      

      The unique identifier for the request that generated the trace's segments and subsegments.

      

      

    Duration -> (double)

      

      The length of time in seconds between the start time of the root segment and the end time of the last segment that completed.

      

      

    Segments -> (list)

      

      Segment documents for the segments and subsegments that comprise the trace.

      

      (structure)

        

        A segment from a trace that has been ingested by the X-Ray service. The segment can be compiled from documents uploaded with  put-trace-segments , or an ``inferred`` segment for a downstream service, generated from a subsegment sent by the service that called it.

        

        Id -> (string)

          

          The segment's ID.

          

          

        Document -> (string)

          

          The segment document

          

          

        

      

    

  

UnprocessedTraceIds -> (list)

  

  Trace IDs of requests that haven't been processed.

  

  (string)

    

    

  

NextToken -> (string)

  

  Pagination token. Not used.

  

  

