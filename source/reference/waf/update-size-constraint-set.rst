[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf update-size-constraint-set:


**************************
update-size-constraint-set
**************************



===========
Description
===========



Inserts or deletes  SizeConstraint objects (filters) in a  SizeConstraintSet . For each ``SizeConstraint`` object, you specify the following values: 

 

 
* Whether to insert or delete the object from the array. If you want to change a ``SizeConstraintSetUpdate`` object, you delete the existing object and add a new one.
 
* The part of a web request that you want AWS WAF to evaluate, such as the length of a query string or the length of the ``User-Agent`` header.
 
* Whether to perform any transformations on the request, such as converting it to lowercase, before checking its length. Note that transformations of the request body are not supported because the AWS resource forwards only the first ``8192`` bytes of your request to AWS WAF.
 
* A ``ComparisonOperator`` used for evaluating the selected part of the request against the specified ``Size`` , such as equals, greater than, less than, and so on.
 
* The length, in bytes, that you want AWS WAF to watch for in selected part of the request. The length is computed after applying the transformation.
 

 

For example, you can add a ``SizeConstraintSetUpdate`` object that matches web requests in which the length of the ``User-Agent`` header is greater than 100 bytes. You can then configure AWS WAF to block those requests.

 

To create and configure a ``SizeConstraintSet`` , perform the following steps:

 

 
* Create a ``SizeConstraintSet.`` For more information, see  create-size-constraint-set .
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of an ``update-size-constraint-set`` request.
 
* Submit an ``update-size-constraint-set`` request to specify the part of the request that you want AWS WAF to inspect (for example, the header or the URI) and the value that you want AWS WAF to watch for.
 

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide`_ .



========
Synopsis
========

::

    update-size-constraint-set
  --size-constraint-set-id <value>
  --change-token <value>
  --updates <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--size-constraint-set-id`` (string)


  The ``SizeConstraintSetId`` of the  SizeConstraintSet that you want to update. ``SizeConstraintSetId`` is returned by  create-size-constraint-set and by  list-size-constraint-sets .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--updates`` (list)


  An array of ``SizeConstraintSetUpdate`` objects that you want to insert into or delete from a  SizeConstraintSet . For more information, see the applicable data types:

   

   
  *  SizeConstraintSetUpdate : Contains ``Action`` and ``SizeConstraint`` 
   
  *  SizeConstraint : Contains ``FieldToMatch`` , ``TextTransformation`` , ``ComparisonOperator`` , and ``Size`` 
   
  *  FieldToMatch : Contains ``Data`` and ``Type`` 
   

  



Shorthand Syntax::

    Action=string,SizeConstraint={FieldToMatch={Type=string,Data=string},TextTransformation=string,ComparisonOperator=string,Size=long} ...




JSON Syntax::

  [
    {
      "Action": "INSERT"|"DELETE",
      "SizeConstraint": {
        "FieldToMatch": {
          "Type": "URI"|"QUERY_STRING"|"HEADER"|"METHOD"|"BODY",
          "Data": "string"
        },
        "TextTransformation": "NONE"|"COMPRESS_WHITE_SPACE"|"HTML_ENTITY_DECODE"|"LOWERCASE"|"CMD_LINE"|"URL_DECODE",
        "ComparisonOperator": "EQ"|"NE"|"LE"|"LT"|"GE"|"GT",
        "Size": long
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

  

  The ``change-token`` that you used to submit the ``update-size-constraint-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  



.. _AWS WAF Developer Guide: http://docs.aws.amazon.com/waf/latest/developerguide/
