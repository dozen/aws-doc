[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf update-web-acl:


**************
update-web-acl
**************



===========
Description
===========



Inserts or deletes  ActivatedRule objects in a ``WebACL`` . Each ``Rule`` identifies web requests that you want to allow, block, or count. When you update a ``WebACL`` , you specify the following values:

 

 
* A default action for the ``WebACL`` , either ``ALLOW`` or ``BLOCK`` . AWS WAF performs the default action if a request doesn't match the criteria in any of the ``Rules`` in a ``WebACL`` . 
 
* The ``Rules`` that you want to add and/or delete. If you want to replace one ``Rule`` with another, you delete the existing ``Rule`` and add the new one. 
 
* For each ``Rule`` , whether you want AWS WAF to allow requests, block requests, or count requests that match the conditions in the ``Rule`` . 
 
* The order in which you want AWS WAF to evaluate the ``Rules`` in a ``WebACL`` . If you add more than one ``Rule`` to a ``WebACL`` , AWS WAF evaluates each request against the ``Rules`` in order based on the value of ``Priority`` . (The ``Rule`` that has the lowest value for ``Priority`` is evaluated first.) When a web request matches all of the predicates (such as ``ByteMatchSets`` and ``IPSets`` ) in a ``Rule`` , AWS WAF immediately takes the corresponding action, allow or block, and doesn't evaluate the request against the remaining ``Rules`` in the ``WebACL`` , if any.  
 

 

To create and configure a ``WebACL`` , perform the following steps:

 

 
* Create and update the predicates that you want to include in ``Rules`` . For more information, see  create-byte-match-set ,  update-byte-match-set ,  create-ip-set ,  update-ip-set ,  create-sql-injection-match-set , and  update-sql-injection-match-set . 
 
* Create and update the ``Rules`` that you want to include in the ``WebACL`` . For more information, see  create-rule and  update-rule . 
 
* Create a ``WebACL`` . See  create-web-acl . 
 
* Use ``get-change-token`` to get the change token that you provide in the ``change-token`` parameter of an  update-web-acl request. 
 
* Submit an ``update-web-acl`` request to specify the ``Rules`` that you want to include in the ``WebACL`` , to specify the default action, and to associate the ``WebACL`` with a CloudFront distribution.  
 

 

Be aware that if you try to add a RATE_BASED rule to a web ACL without setting the rule type when first creating the rule, the  update-web-acl request will fail because the request tries to add a REGULAR rule (the default rule type) with the specified ID, which does not exist. 

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide <http://docs.aws.amazon.com/waf/latest/developerguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-2015-08-24/UpdateWebACL>`_


========
Synopsis
========

::

    update-web-acl
  --web-acl-id <value>
  --change-token <value>
  [--updates <value>]
  [--default-action <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--web-acl-id`` (string)


  The ``WebACLId`` of the  WebACL that you want to update. ``WebACLId`` is returned by  create-web-acl and by  list-web-acls .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--updates`` (list)


  An array of updates to make to the  WebACL .

   

  An array of ``WebACLUpdate`` objects that you want to insert into or delete from a  WebACL . For more information, see the applicable data types:

   

   
  *  WebACLUpdate : Contains ``Action`` and ``ActivatedRule``   
   
  *  ActivatedRule : Contains ``Action`` , ``Priority`` , ``RuleId`` , and ``Type``   
   
  *  default-action : Contains ``Type``   
   

  



Shorthand Syntax::

    Action=string,ActivatedRule={Priority=integer,RuleId=string,Action={Type=string},Type=string} ...




JSON Syntax::

  [
    {
      "Action": "INSERT"|"DELETE",
      "ActivatedRule": {
        "Priority": integer,
        "RuleId": "string",
        "Action": {
          "Type": "BLOCK"|"ALLOW"|"COUNT"
        },
        "Type": "REGULAR"|"RATE_BASED"
      }
    }
    ...
  ]



``--default-action`` (structure)


  A default action for the web ACL, either ALLOW or BLOCK. AWS WAF performs the default action if a request doesn't match the criteria in any of the rules in a web ACL.

  



Shorthand Syntax::

    Type=string




JSON Syntax::

  {
    "Type": "BLOCK"|"ALLOW"|"COUNT"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``update-web-acl`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

