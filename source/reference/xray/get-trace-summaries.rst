[ :ref:`aws <cli:aws>` . :ref:`xray <cli:aws xray>` ]

.. _cli:aws xray get-trace-summaries:


*******************
get-trace-summaries
*******************



===========
Description
===========



Retrieves IDs and metadata for traces available for a specified time frame using an optional filter. To get the full traces, pass the trace IDs to ``batch-get-traces`` .

 

A filter expression can target traced requests that hit specific service nodes or edges, have errors, or come from a known user. For example, the following filter expression targets traces that pass through ``api.example.com`` :

 

 ``service("api.example.com")``  

 

This filter expression finds traces that have an annotation named ``account`` with the value ``12345`` :

 

 ``annotation.account = "12345"``  

 

For a full list of indexed fields and keywords that you can use in filter expressions, see `Using Filter Expressions <http://docs.aws.amazon.com/xray/latest/devguide/xray-console-filters.html>`_ in the *AWS X-Ray Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/xray-2016-04-12/GetTraceSummaries>`_


========
Synopsis
========

::

    get-trace-summaries
  --start-time <value>
  --end-time <value>
  [--sampling | --no-sampling]
  [--filter-expression <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--start-time`` (timestamp)


  The start of the time frame for which to retrieve traces.

  

``--end-time`` (timestamp)


  The end of the time frame for which to retrieve traces.

  

``--sampling`` | ``--no-sampling`` (boolean)


  Set to ``true`` to get summaries for only a subset of available traces.

  

``--filter-expression`` (string)


  Specify a filter expression to retrieve trace summaries for services or requests that meet certain requirements.

  

``--next-token`` (string)


  Specify the pagination token returned by a previous request to retrieve the next page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TraceSummaries -> (list)

  

  Trace IDs and metadata for traces that were found in the specified time frame.

  

  (structure)

    

    Metadata generated from the segment documents in a trace.

    

    Id -> (string)

      

      The unique identifier for the request that generated the trace's segments and subsegments.

      

      

    Duration -> (double)

      

      The length of time in seconds between the start time of the root segment and the end time of the last segment that completed.

      

      

    ResponseTime -> (double)

      

      The length of time in seconds between the start and end times of the root segment. If the service performs work asynchronously, the response time measures the time before the response is sent to the user, while the duration measures the amount of time before the last traced activity completes.

      

      

    HasFault -> (boolean)

      

      One or more of the segment documents has a 500 series error.

      

      

    HasError -> (boolean)

      

      One or more of the segment documents has a 400 series error.

      

      

    HasThrottle -> (boolean)

      

      One or more of the segment documents has a 429 throttling error.

      

      

    IsPartial -> (boolean)

      

      One or more of the segment documents is in progress.

      

      

    Http -> (structure)

      

      Information about the HTTP request served by the trace.

      

      HttpURL -> (string)

        

        The request URL.

        

        

      HttpStatus -> (integer)

        

        The response status.

        

        

      HttpMethod -> (string)

        

        The request method.

        

        

      UserAgent -> (string)

        

        The request's user agent string.

        

        

      ClientIp -> (string)

        

        The IP address of the requestor.

        

        

      

    Annotations -> (map)

      

      Annotations from the trace's segment documents.

      

      key -> (string)

        

        

      value -> (list)

        

        (structure)

          

          Information about a segment annotation.

          

          AnnotationValue -> (structure)

            

            Values of the annotation.

            

            NumberValue -> (double)

              

              Value for a Number annotation.

              

              

            BooleanValue -> (boolean)

              

              Value for a Boolean annotation.

              

              

            StringValue -> (string)

              

              Value for a next-token annotation.

              

              

            

          ServiceIds -> (list)

            

            Services to which the annotation applies.

            

            (structure)

              

              

              

              Name -> (string)

                

                

                

                

              Names -> (list)

                

                

                

                (string)

                  

                  

                

              AccountId -> (string)

                

                

                

                

              Type -> (string)

                

                

                

                

              

            

          

        

      

    Users -> (list)

      

      Users from the trace's segment documents.

      

      (structure)

        

        Information about a user recorded in segment documents.

        

        UserName -> (string)

          

          The user's name.

          

          

        ServiceIds -> (list)

          

          Services that the user's request hit.

          

          (structure)

            

            

            

            Name -> (string)

              

              

              

              

            Names -> (list)

              

              

              

              (string)

                

                

              

            AccountId -> (string)

              

              

              

              

            Type -> (string)

              

              

              

              

            

          

        

      

    ServiceIds -> (list)

      

      Service IDs from the trace's segment documents.

      

      (structure)

        

        

        

        Name -> (string)

          

          

          

          

        Names -> (list)

          

          

          

          (string)

            

            

          

        AccountId -> (string)

          

          

          

          

        Type -> (string)

          

          

          

          

        

      

    

  

ApproximateTime -> (timestamp)

  

  The start time of this page of results.

  

  

TracesProcessedCount -> (long)

  

  The number of traces that were processed to get this set of summaries.

  

  

NextToken -> (string)

  

  If the requested time frame contained more than one page of results, you can use this token to retrieve the next page. The first page contains the most most recent results, closest to the end of the time frame.

  

  

