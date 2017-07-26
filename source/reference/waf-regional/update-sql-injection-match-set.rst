[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional update-sql-injection-match-set:


******************************
update-sql-injection-match-set
******************************



===========
Description
===========



Inserts or deletes  SqlInjectionMatchTuple objects (filters) in a  SqlInjectionMatchSet . For each ``SqlInjectionMatchTuple`` object, you specify the following values:

 

 
* ``Action`` : Whether to insert the object into or delete the object from the array. To change a ``SqlInjectionMatchTuple`` , you delete the existing object and add a new one. 
 
* ``FieldToMatch`` : The part of web requests that you want AWS WAF to inspect and, if you want AWS WAF to inspect a header, the name of the header. 
 
* ``TextTransformation`` : Which text transformation, if any, to perform on the web request before inspecting the request for snippets of malicious SQL code. 
 

 

You use ``SqlInjectionMatchSet`` objects to specify which CloudFront requests you want to allow, block, or count. For example, if you're receiving requests that contain snippets of SQL code in the query string and you want to block the requests, you can create a ``SqlInjectionMatchSet`` with the applicable settings, and then configure AWS WAF to block the requests. 

 

To create and configure a ``SqlInjectionMatchSet`` , perform the following steps:

 

 
* Submit a  create-sql-injection-match-set request. 
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of an  update-ip-set request. 
 
* Submit an ``update-sql-injection-match-set`` request to specify the parts of web requests that you want AWS WAF to inspect for snippets of SQL code. 
 

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide <http://docs.aws.amazon.com/waf/latest/developerguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/UpdateSqlInjectionMatchSet>`_


========
Synopsis
========

::

    update-sql-injection-match-set
  --sql-injection-match-set-id <value>
  --change-token <value>
  --updates <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--sql-injection-match-set-id`` (string)


  The ``SqlInjectionMatchSetId`` of the ``SqlInjectionMatchSet`` that you want to update. ``SqlInjectionMatchSetId`` is returned by  create-sql-injection-match-set and by  list-sql-injection-match-sets .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--updates`` (list)


  An array of ``SqlInjectionMatchSetUpdate`` objects that you want to insert into or delete from a  SqlInjectionMatchSet . For more information, see the applicable data types:

   

   
  *  SqlInjectionMatchSetUpdate : Contains ``Action`` and ``SqlInjectionMatchTuple``   
   
  *  SqlInjectionMatchTuple : Contains ``FieldToMatch`` and ``TextTransformation``   
   
  *  FieldToMatch : Contains ``Data`` and ``Type``   
   

  



Shorthand Syntax::

    Action=string,SqlInjectionMatchTuple={FieldToMatch={Type=string,Data=string},TextTransformation=string} ...




JSON Syntax::

  [
    {
      "Action": "INSERT"|"DELETE",
      "SqlInjectionMatchTuple": {
        "FieldToMatch": {
          "Type": "URI"|"QUERY_STRING"|"HEADER"|"METHOD"|"BODY",
          "Data": "string"
        },
        "TextTransformation": "NONE"|"COMPRESS_WHITE_SPACE"|"HTML_ENTITY_DECODE"|"LOWERCASE"|"CMD_LINE"|"URL_DECODE"
      }
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``update-sql-injection-match-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

