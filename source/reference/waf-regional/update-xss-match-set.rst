[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional update-xss-match-set:


********************
update-xss-match-set
********************



===========
Description
===========



Inserts or deletes  XssMatchTuple objects (filters) in an  XssMatchSet . For each ``XssMatchTuple`` object, you specify the following values:

 

 
* ``Action`` : Whether to insert the object into or delete the object from the array. To change a ``XssMatchTuple`` , you delete the existing object and add a new one. 
 
* ``FieldToMatch`` : The part of web requests that you want AWS WAF to inspect and, if you want AWS WAF to inspect a header, the name of the header. 
 
* ``TextTransformation`` : Which text transformation, if any, to perform on the web request before inspecting the request for cross-site scripting attacks. 
 

 

You use ``XssMatchSet`` objects to specify which CloudFront requests you want to allow, block, or count. For example, if you're receiving requests that contain cross-site scripting attacks in the request body and you want to block the requests, you can create an ``XssMatchSet`` with the applicable settings, and then configure AWS WAF to block the requests. 

 

To create and configure an ``XssMatchSet`` , perform the following steps:

 

 
* Submit a  create-xss-match-set request. 
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of an  update-ip-set request. 
 
* Submit an ``update-xss-match-set`` request to specify the parts of web requests that you want AWS WAF to inspect for cross-site scripting attacks. 
 

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide <http://docs.aws.amazon.com/waf/latest/developerguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/UpdateXssMatchSet>`_


========
Synopsis
========

::

    update-xss-match-set
  --xss-match-set-id <value>
  --change-token <value>
  --updates <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--xss-match-set-id`` (string)


  The ``XssMatchSetId`` of the ``XssMatchSet`` that you want to update. ``XssMatchSetId`` is returned by  create-xss-match-set and by  list-xss-match-sets .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--updates`` (list)


  An array of ``XssMatchSetUpdate`` objects that you want to insert into or delete from a  XssMatchSet . For more information, see the applicable data types:

   

   
  *  XssMatchSetUpdate : Contains ``Action`` and ``XssMatchTuple``   
   
  *  XssMatchTuple : Contains ``FieldToMatch`` and ``TextTransformation``   
   
  *  FieldToMatch : Contains ``Data`` and ``Type``   
   

  



Shorthand Syntax::

    Action=string,XssMatchTuple={FieldToMatch={Type=string,Data=string},TextTransformation=string} ...




JSON Syntax::

  [
    {
      "Action": "INSERT"|"DELETE",
      "XssMatchTuple": {
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

  

  The ``change-token`` that you used to submit the ``update-xss-match-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

