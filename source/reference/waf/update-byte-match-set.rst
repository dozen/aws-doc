[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf update-byte-match-set:


*********************
update-byte-match-set
*********************



===========
Description
===========



Inserts or deletes  ByteMatchTuple objects (filters) in a  ByteMatchSet . For each ``ByteMatchTuple`` object, you specify the following values: 

 

 
* Whether to insert or delete the object from the array. If you want to change a ``ByteMatchSetUpdate`` object, you delete the existing object and add a new one.
 
* The part of a web request that you want AWS WAF to inspect, such as a query string or the value of the ``User-Agent`` header. 
 
* The bytes (typically a string that corresponds with ASCII characters) that you want AWS WAF to look for. For more information, including how you specify the values for the AWS WAF API and the AWS CLI or SDKs, see ``TargetString`` in the  ByteMatchTuple data type. 
 
* Where to look, such as at the beginning or the end of a query string.
 
* Whether to perform any conversions on the request, such as converting it to lowercase, before inspecting it for the specified string.
 

 

For example, you can add a ``ByteMatchSetUpdate`` object that matches web requests in which ``User-Agent`` headers contain the string ``BadBot`` . You can then configure AWS WAF to block those requests.

 

To create and configure a ``ByteMatchSet`` , perform the following steps:

 

 
* Create a ``ByteMatchSet.`` For more information, see  create-byte-match-set .
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of an ``update-byte-match-set`` request.
 
* Submit an ``update-byte-match-set`` request to specify the part of the request that you want AWS WAF to inspect (for example, the header or the URI) and the value that you want AWS WAF to watch for.
 

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .



========
Synopsis
========

::

    update-byte-match-set
  --byte-match-set-id <value>
  --change-token <value>
  --updates <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--byte-match-set-id`` (string)


  The ``ByteMatchSetId`` of the  ByteMatchSet that you want to update. ``ByteMatchSetId`` is returned by  create-byte-match-set and by  list-byte-match-sets .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--updates`` (list)


  An array of ``ByteMatchSetUpdate`` objects that you want to insert into or delete from a  ByteMatchSet . For more information, see the applicable data types:

   

   
  *  ByteMatchSetUpdate : Contains ``Action`` and ``ByteMatchTuple`` 
   
  *  ByteMatchTuple : Contains ``FieldToMatch`` , ``PositionalConstraint`` , ``TargetString`` , and ``TextTransformation`` 
   
  *  FieldToMatch : Contains ``Data`` and ``Type`` 
   

  



Shorthand Syntax::

    Action=string,ByteMatchTuple={FieldToMatch={Type=string,Data=string},TargetString=blob,TextTransformation=string,PositionalConstraint=string} ...




JSON Syntax::

  [
    {
      "Action": "INSERT"|"DELETE",
      "ByteMatchTuple": {
        "FieldToMatch": {
          "Type": "URI"|"QUERY_STRING"|"HEADER"|"METHOD"|"BODY",
          "Data": "string"
        },
        "TargetString": blob,
        "TextTransformation": "NONE"|"COMPRESS_WHITE_SPACE"|"HTML_ENTITY_DECODE"|"LOWERCASE"|"CMD_LINE"|"URL_DECODE",
        "PositionalConstraint": "EXACTLY"|"STARTS_WITH"|"ENDS_WITH"|"CONTAINS"|"CONTAINS_WORD"
      }
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

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``update-byte-match-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  



.. _AWS WAF Developer Guide: http://docs.aws.amazon.com/waf/latest/developerguide/
