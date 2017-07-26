[ :ref:`aws <cli:aws>` . :ref:`xray <cli:aws xray>` ]

.. _cli:aws xray get-trace-graph:


***************
get-trace-graph
***************



===========
Description
===========



Retrieves a service graph for one or more specific trace IDs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/xray-2016-04-12/GetTraceGraph>`_


========
Synopsis
========

::

    get-trace-graph
  --trace-ids <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--trace-ids`` (list)


  Trace IDs of requests for which to generate a service graph.

  



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

Services -> (list)

  

  The services that have processed one of the specified requests.

  

  (structure)

    

    Information about an application that processed requests, users that made requests, or downstream services, resources and applications that an application used.

    

    ReferenceId -> (integer)

      

      Identifier for the service. Unique within the service map.

      

      

    Name -> (string)

      

      The canonical name of the service.

      

      

    Names -> (list)

      

      A list of names for the service, including the canonical name.

      

      (string)

        

        

      

    Root -> (boolean)

      

      Indicates that the service was the first service to process a request.

      

      

    AccountId -> (string)

      

      Identifier of the AWS account in which the service runs.

      

      

    Type -> (string)

      

      The type of service.

       

       
      * AWS Resource - The type of an AWS resource. For example, ``AWS::EC2::Instance`` for a application running on Amazon EC2 or ``AWS::DynamoDB::Table`` for an Amazon DynamoDB table that the application used. 
       
      * AWS Service - The type of an AWS service. For example, ``AWS::DynamoDB`` for downstream calls to Amazon DynamoDB that didn't target a specific table. 
       
      * ``client`` - Represents the clients that sent requests to a root service. 
       
      * ``remote`` - A downstream service of indeterminate type. 
       

      

      

    State -> (string)

      

      The service's state.

      

      

    StartTime -> (timestamp)

      

      The start time of the first segment that the service generated.

      

      

    EndTime -> (timestamp)

      

      The end time of the last segment that the service generated.

      

      

    Edges -> (list)

      

      Connections to downstream services.

      

      (structure)

        

        Information about a connection between two services.

        

        ReferenceId -> (integer)

          

          Identifier of the edge. Unique within a service map.

          

          

        StartTime -> (timestamp)

          

          The start time of the first segment on the edge.

          

          

        EndTime -> (timestamp)

          

          The end time of the last segment on the edge.

          

          

        SummaryStatistics -> (structure)

          

          Response statistics for segments on the edge.

          

          OkCount -> (long)

            

            The number of requests that completed with a 2xx Success status code.

            

            

          ErrorStatistics -> (structure)

            

            Information about requests that failed with a 4xx Client Error status code.

            

            ThrottleCount -> (long)

              

              The number of requests that failed with a 419 throttling status code.

              

              

            OtherCount -> (long)

              

              The number of requests that failed with untracked 4xx Client Error status codes.

              

              

            TotalCount -> (long)

              

              The total number of requests that failed with a 4xx Client Error status code.

              

              

            

          FaultStatistics -> (structure)

            

            Information about requests that failed with a 5xx Server Error status code.

            

            OtherCount -> (long)

              

              The number of requests that failed with untracked 5xx Server Error status codes.

              

              

            TotalCount -> (long)

              

              The total number of requests that failed with a 5xx Server Error status code.

              

              

            

          TotalCount -> (long)

            

            The total number of completed requests.

            

            

          TotalResponseTime -> (double)

            

            The aggregate response time of completed requests.

            

            

          

        ResponseTimeHistogram -> (list)

          

          A histogram that maps the spread of client response times on an edge.

          

          (structure)

            

            An entry in a histogram for a statistic. A histogram maps the range of observed values on the X axis, and the prevalence of each value on the Y axis.

            

            Value -> (double)

              

              The value of the entry.

              

              

            Count -> (integer)

              

              The prevalence of the entry.

              

              

            

          

        Aliases -> (list)

          

          Aliases for the edge.

          

          (structure)

            

            An alias for an edge.

            

            Name -> (string)

              

              The canonical name of the alias.

              

              

            Names -> (list)

              

              A list of names for the alias, including the canonical name.

              

              (string)

                

                

              

            Type -> (string)

              

              The type of the alias.

              

              

            

          

        

      

    SummaryStatistics -> (structure)

      

      Aggregated statistics for the service.

      

      OkCount -> (long)

        

        The number of requests that completed with a 2xx Success status code.

        

        

      ErrorStatistics -> (structure)

        

        Information about requests that failed with a 4xx Client Error status code.

        

        ThrottleCount -> (long)

          

          The number of requests that failed with a 419 throttling status code.

          

          

        OtherCount -> (long)

          

          The number of requests that failed with untracked 4xx Client Error status codes.

          

          

        TotalCount -> (long)

          

          The total number of requests that failed with a 4xx Client Error status code.

          

          

        

      FaultStatistics -> (structure)

        

        Information about requests that failed with a 5xx Server Error status code.

        

        OtherCount -> (long)

          

          The number of requests that failed with untracked 5xx Server Error status codes.

          

          

        TotalCount -> (long)

          

          The total number of requests that failed with a 5xx Server Error status code.

          

          

        

      TotalCount -> (long)

        

        The total number of completed requests.

        

        

      TotalResponseTime -> (double)

        

        The aggregate response time of completed requests.

        

        

      

    DurationHistogram -> (list)

      

      A histogram that maps the spread of service durations.

      

      (structure)

        

        An entry in a histogram for a statistic. A histogram maps the range of observed values on the X axis, and the prevalence of each value on the Y axis.

        

        Value -> (double)

          

          The value of the entry.

          

          

        Count -> (integer)

          

          The prevalence of the entry.

          

          

        

      

    ResponseTimeHistogram -> (list)

      

      A histogram that maps the spread of service response times.

      

      (structure)

        

        An entry in a histogram for a statistic. A histogram maps the range of observed values on the X axis, and the prevalence of each value on the Y axis.

        

        Value -> (double)

          

          The value of the entry.

          

          

        Count -> (integer)

          

          The prevalence of the entry.

          

          

        

      

    

  

NextToken -> (string)

  

  Pagination token. Not used.

  

  

