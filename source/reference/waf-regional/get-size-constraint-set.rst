[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional get-size-constraint-set:


***********************
get-size-constraint-set
***********************



===========
Description
===========



Returns the  SizeConstraintSet specified by ``SizeConstraintSetId`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/GetSizeConstraintSet>`_


========
Synopsis
========

::

    get-size-constraint-set
  --size-constraint-set-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--size-constraint-set-id`` (string)


  The ``SizeConstraintSetId`` of the  SizeConstraintSet that you want to get. ``SizeConstraintSetId`` is returned by  create-size-constraint-set and by  list-size-constraint-sets .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SizeConstraintSet -> (structure)

  

  Information about the  SizeConstraintSet that you specified in the ``get-size-constraint-set`` request. For more information, see the following topics:

   

   
  *  SizeConstraintSet : Contains ``SizeConstraintSetId`` , ``SizeConstraints`` , and ``Name``   
   
  * ``SizeConstraints`` : Contains an array of  SizeConstraint objects. Each ``SizeConstraint`` object contains  FieldToMatch , ``TextTransformation`` , ``ComparisonOperator`` , and ``Size``   
   
  *  FieldToMatch : Contains ``Data`` and ``Type``   
   

  

  SizeConstraintSetId -> (string)

    

    A unique identifier for a ``SizeConstraintSet`` . You use ``SizeConstraintSetId`` to get information about a ``SizeConstraintSet`` (see  get-size-constraint-set ), update a ``SizeConstraintSet`` (see  update-size-constraint-set ), insert a ``SizeConstraintSet`` into a ``Rule`` or delete one from a ``Rule`` (see  update-rule ), and delete a ``SizeConstraintSet`` from AWS WAF (see  delete-size-constraint-set ).

     

     ``SizeConstraintSetId`` is returned by  create-size-constraint-set and by  list-size-constraint-sets .

    

    

  Name -> (string)

    

    The name, if any, of the ``SizeConstraintSet`` .

    

    

  SizeConstraints -> (list)

    

    Specifies the parts of web requests that you want to inspect the size of.

    

    (structure)

      

      Specifies a constraint on the size of a part of the web request. AWS WAF uses the ``Size`` , ``ComparisonOperator`` , and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

      

      FieldToMatch -> (structure)

        

        Specifies where in a web request to look for the size constraint.

        

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

         

        Note that if you choose ``BODY`` for the value of ``Type`` , you must choose ``NONE`` for ``TextTransformation`` because CloudFront forwards only the first 8192 bytes for inspection. 

         

         **NONE**  

         

        Specify ``NONE`` if you don't want to perform any text transformations.

         

         **CMD_LINE**  

         

        When you're concerned that attackers are injecting an operating system command line command and using unusual formatting to disguise some or all of the command, use this option to perform the following transformations:

         

         
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

        

        

      ComparisonOperator -> (string)

        

        The type of comparison you want AWS WAF to perform. AWS WAF uses this in combination with the provided ``Size`` and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

         

         **EQ** : Used to test if the ``Size`` is equal to the size of the ``FieldToMatch``  

         

         **NE** : Used to test if the ``Size`` is not equal to the size of the ``FieldToMatch``  

         

         **LE** : Used to test if the ``Size`` is less than or equal to the size of the ``FieldToMatch``  

         

         **LT** : Used to test if the ``Size`` is strictly less than the size of the ``FieldToMatch``  

         

         **GE** : Used to test if the ``Size`` is greater than or equal to the size of the ``FieldToMatch``  

         

         **GT** : Used to test if the ``Size`` is strictly greater than the size of the ``FieldToMatch``  

        

        

      Size -> (long)

        

        The size in bytes that you want AWS WAF to compare against the size of the specified ``FieldToMatch`` . AWS WAF uses this in combination with ``ComparisonOperator`` and ``FieldToMatch`` to build an expression in the form of "``Size``  ``ComparisonOperator`` size in bytes of ``FieldToMatch`` ". If that expression is true, the ``SizeConstraint`` is considered to match.

         

        Valid values for size are 0 - 21474836480 bytes (0 - 20 GB).

         

        If you specify ``URI`` for the value of ``Type`` , the / in the URI counts as one character. For example, the URI ``/logo.jpg`` is nine characters long.

        

        

      

    

  

