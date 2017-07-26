[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional get-sampled-requests:


********************
get-sampled-requests
********************



===========
Description
===========



Gets detailed information about a specified number of requests--a sample--that AWS WAF randomly selects from among the first 5,000 requests that your AWS resource received during a time range that you choose. You can specify a sample size of up to 500 requests, and you can specify any time range in the previous three hours.

 

 ``get-sampled-requests`` returns a time range, which is usually the time range that you specified. However, if your resource (such as a CloudFront distribution) received 5,000 requests before the specified time range elapsed, ``get-sampled-requests`` returns an updated time range. This new time range indicates the actual period during which AWS WAF selected the requests in the sample.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/GetSampledRequests>`_


========
Synopsis
========

::

    get-sampled-requests
  --web-acl-id <value>
  --rule-id <value>
  --time-window <value>
  --max-items <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--web-acl-id`` (string)


  The ``WebACLId`` of the ``WebACL`` for which you want ``get-sampled-requests`` to return a sample of requests.

  

``--rule-id`` (string)


   ``RuleId`` is one of two values:

   

   
  * The ``RuleId`` of the ``Rule`` for which you want ``get-sampled-requests`` to return a sample of requests. 
   
  * ``Default_Action`` , which causes ``get-sampled-requests`` to return a sample of the requests that didn't match any of the rules in the specified ``WebACL`` . 
   

  

``--time-window`` (structure)


  The start date and time and the end date and time of the range for which you want ``get-sampled-requests`` to return a sample of requests. Specify the date and time in the following format: ``"2016-09-27T14:50Z"`` . You can specify any time range in the previous three hours.

  



Shorthand Syntax::

    StartTime=timestamp,EndTime=timestamp




JSON Syntax::

  {
    "StartTime": timestamp,
    "EndTime": timestamp
  }



``--max-items`` (long)


  The number of requests that you want AWS WAF to return from among the first 5,000 requests that your AWS resource received during the time range. If your resource received fewer requests than the value of ``MaxItems`` , ``get-sampled-requests`` returns information about all of them. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SampledRequests -> (list)

  

  A complex type that contains detailed information about each of the requests in the sample.

  

  (structure)

    

    The response from a  get-sampled-requests request includes a ``SampledHTTPRequests`` complex type that appears as ``SampledRequests`` in the response syntax. ``SampledHTTPRequests`` contains one ``SampledHTTPRequest`` object for each web request that is returned by ``get-sampled-requests`` .

    

    Request -> (structure)

      

      A complex type that contains detailed information about the request.

      

      ClientIP -> (string)

        

        The IP address that the request originated from. If the ``WebACL`` is associated with a CloudFront distribution, this is the value of one of the following fields in CloudFront access logs:

         

         
        * ``c-ip`` , if the viewer did not use an HTTP proxy or a load balancer to send the request 
         
        * ``x-forwarded-for`` , if the viewer did use an HTTP proxy or a load balancer to send the request 
         

        

        

      Country -> (string)

        

        The two-letter country code for the country that the request originated from. For a current list of country codes, see the Wikipedia entry `ISO 3166-1 alpha-2 <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2>`_ .

        

        

      URI -> (string)

        

        The part of a web request that identifies the resource, for example, ``/images/daily-ad.jpg`` .

        

        

      Method -> (string)

        

        The HTTP method specified in the sampled web request. CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` . 

        

        

      HTTPVersion -> (string)

        

        The HTTP version specified in the sampled web request, for example, ``HTTP/1.1`` .

        

        

      Headers -> (list)

        

        A complex type that contains two values for each header in the sampled web request: the name of the header and the value of the header.

        

        (structure)

          

          The response from a  get-sampled-requests request includes an ``HTTPHeader`` complex type that appears as ``Headers`` in the response syntax. ``HTTPHeader`` contains the names and values of all of the headers that appear in one of the web requests that were returned by ``get-sampled-requests`` . 

          

          Name -> (string)

            

            The name of one of the headers in the sampled web request.

            

            

          Value -> (string)

            

            The value of one of the headers in the sampled web request.

            

            

          

        

      

    Weight -> (long)

      

      A value that indicates how one result in the response relates proportionally to other results in the response. A result that has a weight of ``2`` represents roughly twice as many CloudFront web requests as a result that has a weight of ``1`` .

      

      

    Timestamp -> (timestamp)

      

      The time at which AWS WAF received the request from your AWS resource, in Unix time format (in seconds).

      

      

    Action -> (string)

      

      The action for the ``Rule`` that the request matched: ``ALLOW`` , ``BLOCK`` , or ``COUNT`` .

      

      

    

  

PopulationSize -> (long)

  

  The total number of requests from which ``get-sampled-requests`` got a sample of ``MaxItems`` requests. If ``PopulationSize`` is less than ``MaxItems`` , the sample includes every request that your AWS resource received during the specified time range.

  

  

TimeWindow -> (structure)

  

  Usually, ``time-window`` is the time range that you specified in the ``get-sampled-requests`` request. However, if your AWS resource received more than 5,000 requests during the time range that you specified in the request, ``get-sampled-requests`` returns the time range for the first 5,000 requests.

  

  StartTime -> (timestamp)

    

    The beginning of the time range from which you want ``get-sampled-requests`` to return a sample of the requests that your AWS resource received. Specify the date and time in the following format: ``"2016-09-27T14:50Z"`` . You can specify any time range in the previous three hours.

    

    

  EndTime -> (timestamp)

    

    The end of the time range from which you want ``get-sampled-requests`` to return a sample of the requests that your AWS resource received. Specify the date and time in the following format: ``"2016-09-27T14:50Z"`` . You can specify any time range in the previous three hours.

    

    

  

