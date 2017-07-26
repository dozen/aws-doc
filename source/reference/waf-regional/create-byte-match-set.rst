[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional create-byte-match-set:


*********************
create-byte-match-set
*********************



===========
Description
===========



Creates a ``ByteMatchSet`` . You then use  update-byte-match-set to identify the part of a web request that you want AWS WAF to inspect, such as the values of the ``User-Agent`` header or the query string. For example, you can create a ``ByteMatchSet`` that matches any requests with ``User-Agent`` headers that contain the string ``BadBot`` . You can then configure AWS WAF to reject those requests.

 

To create and configure a ``ByteMatchSet`` , perform the following steps:

 

 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``create-byte-match-set`` request. 
 
* Submit a ``create-byte-match-set`` request. 
 
* Use ``get-change-token`` to get the change token that you provide in the ``change-token`` parameter of an ``update-byte-match-set`` request. 
 
* Submit an  update-byte-match-set request to specify the part of the request that you want AWS WAF to inspect (for example, the header or the URI) and the value that you want AWS WAF to watch for. 
 

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide <http://docs.aws.amazon.com/waf/latest/developerguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/CreateByteMatchSet>`_


========
Synopsis
========

::

    create-byte-match-set
  --name <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  A friendly name or description of the  ByteMatchSet . You can't change ``Name`` after you create a ``ByteMatchSet`` .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ByteMatchSet -> (structure)

  

  A  ByteMatchSet that contains no ``ByteMatchTuple`` objects.

  

  ByteMatchSetId -> (string)

    

    The ``ByteMatchSetId`` for a ``ByteMatchSet`` . You use ``ByteMatchSetId`` to get information about a ``ByteMatchSet`` (see  get-byte-match-set ), update a ``ByteMatchSet`` (see  update-byte-match-set ), insert a ``ByteMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  update-rule ), and delete a ``ByteMatchSet`` from AWS WAF (see  delete-byte-match-set ).

     

     ``ByteMatchSetId`` is returned by  create-byte-match-set and by  list-byte-match-sets .

    

    

  Name -> (string)

    

    A friendly name or description of the  ByteMatchSet . You can't change ``Name`` after you create a ``ByteMatchSet`` .

    

    

  ByteMatchTuples -> (list)

    

    Specifies the bytes (typically a string that corresponds with ASCII characters) that you want AWS WAF to search for in web requests, the location in requests that you want AWS WAF to search, and other settings.

    

    (structure)

      

      The bytes (typically a string that corresponds with ASCII characters) that you want AWS WAF to search for in web requests, the location in requests that you want AWS WAF to search, and other settings.

      

      FieldToMatch -> (structure)

        

        The part of a web request that you want AWS WAF to search, such as a specified header or a query string. For more information, see  FieldToMatch .

        

        Type -> (string)

          

          The part of the web request that you want AWS WAF to search for a specified string. Parts of a request that you can search include the following:

           

           
          * ``HEADER`` : A specified request header, for example, the value of the ``User-Agent`` or ``Referer`` header. If you choose ``HEADER`` for the type, specify the name of the header in ``Data`` . 
           
          * ``METHOD`` : The HTTP method, which indicated the type of operation that the request is asking the origin to perform. Amazon CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` . 
           
          * ``QUERY_STRING`` : A query string, which is the part of a URL that appears after a ``?`` character, if any. 
           
          * ``URI`` : The part of a web request that identifies a resource, for example, ``/images/daily-ad.jpg`` . 
           
          * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  create-size-constraint-set .  
           

          

          

        Data -> (string)

          

          When the value of ``Type`` is ``HEADER`` , enter the name of the header that you want AWS WAF to search, for example, ``User-Agent`` or ``Referer`` . If the value of ``Type`` is any other value, omit ``Data`` .

           

          The name of the header is not case sensitive.

          

          

        

      TargetString -> (blob)

        

        The value that you want AWS WAF to search for. AWS WAF searches for the specified string in the part of web requests that you specified in ``FieldToMatch`` . The maximum length of the value is 50 bytes.

         

        Valid values depend on the values that you specified for ``FieldToMatch`` :

         

         
        * ``HEADER`` : The value that you want AWS WAF to search for in the request header that you specified in  FieldToMatch , for example, the value of the ``User-Agent`` or ``Referer`` header. 
         
        * ``METHOD`` : The HTTP method, which indicates the type of operation specified in the request. CloudFront supports the following methods: ``DELETE`` , ``GET`` , ``HEAD`` , ``OPTIONS`` , ``PATCH`` , ``POST`` , and ``PUT`` . 
         
        * ``QUERY_STRING`` : The value that you want AWS WAF to search for in the query string, which is the part of a URL that appears after a ``?`` character. 
         
        * ``URI`` : The value that you want AWS WAF to search for in the part of a URL that identifies a resource, for example, ``/images/daily-ad.jpg`` . 
         
        * ``BODY`` : The part of a request that contains any additional data that you want to send to your web server as the HTTP request body, such as data from a form. The request body immediately follows the request headers. Note that only the first ``8192`` bytes of the request body are forwarded to AWS WAF for inspection. To allow or block requests based on the length of the body, you can create a size constraint set. For more information, see  create-size-constraint-set .  
         

         

        If ``TargetString`` includes alphabetic characters A-Z and a-z, note that the value is case sensitive.

         

         **If you're using the AWS WAF API**  

         

        Specify a base64-encoded version of the value. The maximum length of the value before you base64-encode it is 50 bytes.

         

        For example, suppose the value of ``Type`` is ``HEADER`` and the value of ``Data`` is ``User-Agent`` . If you want to search the ``User-Agent`` header for the value ``BadBot`` , you base64-encode ``BadBot`` using MIME base64 encoding and include the resulting value, ``QmFkQm90`` , in the value of ``TargetString`` .

         

         **If you're using the AWS CLI or one of the AWS SDKs**  

         

        The value that you want AWS WAF to search for. The SDK automatically base64 encodes the value.

        

        

      TextTransformation -> (string)

        

        Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``TargetString`` before inspecting a request for a match.

         

         **CMD_LINE**  

         

        When you're concerned that attackers are injecting an operating system commandline command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

         

         
        * Delete the following characters: \ " ' ^ 
         
        * Delete spaces before the following characters: / ( 
         
        * Replace the following characters with a space: , ; 
         
        * Replace multiple spaces with one space 
         
        * Convert uppercase letters (A-Z) to lowercase (a-z) 
         

         

         **COMPRESS_WHITE_SPACE**  

         

        Use this option to replace the following characters with a space character (decimal 32):

         

         
        * \f, formfeed, decimal 12 
         
        * \t, tab, decimal 9 
         
        * \n, newline, decimal 10 
         
        * \r, carriage return, decimal 13 
         
        * \v, vertical tab, decimal 11 
         
        * non-breaking space, decimal 160 
         

         

         ``COMPRESS_WHITE_SPACE`` also replaces multiple spaces with one space.

         

         **HTML_ENTITY_DECODE**  

         

        Use this option to replace HTML-encoded characters with unencoded characters. ``HTML_ENTITY_DECODE`` performs the following operations:

         

         
        * Replaces ``(ampersand)quot;`` with ``"``   
         
        * Replaces ``(ampersand)nbsp;`` with a non-breaking space, decimal 160 
         
        * Replaces ``(ampersand)lt;`` with a "less than" symbol 
         
        * Replaces ``(ampersand)gt;`` with ````   
         
        * Replaces characters that are represented in hexadecimal format, ``(ampersand)#xhhhh;`` , with the corresponding characters 
         
        * Replaces characters that are represented in decimal format, ``(ampersand)#nnnn;`` , with the corresponding characters 
         

         

         **LOWERCASE**  

         

        Use this option to convert uppercase letters (A-Z) to lowercase (a-z).

         

         **URL_DECODE**  

         

        Use this option to decode a URL-encoded value.

         

         **NONE**  

         

        Specify ``NONE`` if you don't want to perform any text transformations.

        

        

      PositionalConstraint -> (string)

        

        Within the portion of a web request that you want to search (for example, in the query string, if any), specify where you want AWS WAF to search. Valid values include the following:

         

         **CONTAINS**  

         

        The specified part of the web request must include the value of ``TargetString`` , but the location doesn't matter.

         

         **CONTAINS_WORD**  

         

        The specified part of the web request must include the value of ``TargetString`` , and ``TargetString`` must contain only alphanumeric characters or underscore (A-Z, a-z, 0-9, or _). In addition, ``TargetString`` must be a word, which means one of the following:

         

         
        * ``TargetString`` exactly matches the value of the specified part of the web request, such as the value of a header. 
         
        * ``TargetString`` is at the beginning of the specified part of the web request and is followed by a character other than an alphanumeric character or underscore (_), for example, ``BadBot;`` . 
         
        * ``TargetString`` is at the end of the specified part of the web request and is preceded by a character other than an alphanumeric character or underscore (_), for example, ``;BadBot`` . 
         
        * ``TargetString`` is in the middle of the specified part of the web request and is preceded and followed by characters other than alphanumeric characters or underscore (_), for example, ``-BadBot;`` . 
         

         

         **EXACTLY**  

         

        The value of the specified part of the web request must exactly match the value of ``TargetString`` .

         

         **STARTS_WITH**  

         

        The value of ``TargetString`` must appear at the beginning of the specified part of the web request.

         

         **ENDS_WITH**  

         

        The value of ``TargetString`` must appear at the end of the specified part of the web request.

        

        

      

    

  

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``create-byte-match-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

