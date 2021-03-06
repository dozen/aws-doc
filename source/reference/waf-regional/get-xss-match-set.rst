[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional get-xss-match-set:


*****************
get-xss-match-set
*****************



===========
Description
===========



Returns the  XssMatchSet that is specified by ``XssMatchSetId`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/GetXssMatchSet>`_


========
Synopsis
========

::

    get-xss-match-set
  --xss-match-set-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--xss-match-set-id`` (string)


  The ``XssMatchSetId`` of the  XssMatchSet that you want to get. ``XssMatchSetId`` is returned by  create-xss-match-set and by  list-xss-match-sets .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

XssMatchSet -> (structure)

  

  Information about the  XssMatchSet that you specified in the ``get-xss-match-set`` request. For more information, see the following topics:

   

   
  *  XssMatchSet : Contains ``Name`` , ``XssMatchSetId`` , and an array of ``XssMatchTuple`` objects 
   
  *  XssMatchTuple : Each ``XssMatchTuple`` object contains ``FieldToMatch`` and ``TextTransformation``   
   
  *  FieldToMatch : Contains ``Data`` and ``Type``   
   

  

  XssMatchSetId -> (string)

    

    A unique identifier for an ``XssMatchSet`` . You use ``XssMatchSetId`` to get information about an ``XssMatchSet`` (see  get-xss-match-set ), update an ``XssMatchSet`` (see  update-xss-match-set ), insert an ``XssMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  update-rule ), and delete an ``XssMatchSet`` from AWS WAF (see  delete-xss-match-set ).

     

     ``XssMatchSetId`` is returned by  create-xss-match-set and by  list-xss-match-sets .

    

    

  Name -> (string)

    

    The name, if any, of the ``XssMatchSet`` .

    

    

  XssMatchTuples -> (list)

    

    Specifies the parts of web requests that you want to inspect for cross-site scripting attacks.

    

    (structure)

      

      Specifies the part of a web request that you want AWS WAF to inspect for cross-site scripting attacks and, if you want AWS WAF to inspect a header, the name of the header.

      

      FieldToMatch -> (structure)

        

        Specifies where in a web request to look for cross-site scripting attacks.

        

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

          

          

        

      TextTransformation -> (string)

        

        Text transformations eliminate some of the unusual formatting that attackers use in web requests in an effort to bypass AWS WAF. If you specify a transformation, AWS WAF performs the transformation on ``FieldToMatch`` before inspecting a request for a match.

         

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

        

        

      

    

  

