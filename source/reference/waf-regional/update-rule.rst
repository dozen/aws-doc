[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional update-rule:


***********
update-rule
***********



===========
Description
===========



Inserts or deletes  Predicate objects in a ``Rule`` . Each ``Predicate`` object identifies a predicate, such as a  ByteMatchSet or an  IPSet , that specifies the web requests that you want to allow, block, or count. If you add more than one predicate to a ``Rule`` , a request must match all of the specifications to be allowed, blocked, or counted. For example, suppose you add the following to a ``Rule`` : 

 

 
* A ``ByteMatchSet`` that matches the value ``BadBot`` in the ``User-Agent`` header 
 
* An ``IPSet`` that matches the IP address ``192.0.2.44``   
 

 

You then add the ``Rule`` to a ``WebACL`` and specify that you want to block requests that satisfy the ``Rule`` . For a request to be blocked, the ``User-Agent`` header in the request must contain the value ``BadBot``  *and* the request must originate from the IP address 192.0.2.44.

 

To create and configure a ``Rule`` , perform the following steps:

 

 
* Create and update the predicates that you want to include in the ``Rule`` . 
 
* Create the ``Rule`` . See  create-rule . 
 
* Use ``get-change-token`` to get the change token that you provide in the ``change-token`` parameter of an  update-rule request. 
 
* Submit an ``update-rule`` request to add predicates to the ``Rule`` . 
 
* Create and update a ``WebACL`` that contains the ``Rule`` . See  create-web-acl . 
 

 

If you want to replace one ``ByteMatchSet`` or ``IPSet`` with another, you delete the existing one and add the new one.

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide <http://docs.aws.amazon.com/waf/latest/developerguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/UpdateRule>`_


========
Synopsis
========

::

    update-rule
  --rule-id <value>
  --change-token <value>
  --updates <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-id`` (string)


  The ``RuleId`` of the ``Rule`` that you want to update. ``RuleId`` is returned by ``create-rule`` and by  list-rules .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--updates`` (list)


  An array of ``RuleUpdate`` objects that you want to insert into or delete from a  Rule . For more information, see the applicable data types:

   

   
  *  RuleUpdate : Contains ``Action`` and ``Predicate``   
   
  *  Predicate : Contains ``DataId`` , ``Negated`` , and ``Type``   
   
  *  FieldToMatch : Contains ``Data`` and ``Type``   
   

  



Shorthand Syntax::

    Action=string,Predicate={Negated=boolean,Type=string,DataId=string} ...




JSON Syntax::

  [
    {
      "Action": "INSERT"|"DELETE",
      "Predicate": {
        "Negated": true|false,
        "Type": "IPMatch"|"ByteMatch"|"SqlInjectionMatch"|"SizeConstraint"|"XssMatch",
        "DataId": "string"
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

  

  The ``change-token`` that you used to submit the ``update-rule`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

