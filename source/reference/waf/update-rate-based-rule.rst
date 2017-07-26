[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf update-rate-based-rule:


**********************
update-rate-based-rule
**********************



===========
Description
===========



Inserts or deletes  Predicate objects in a rule and updates the ``rate-limit`` in the rule. 

 

Each ``Predicate`` object identifies a predicate, such as a  ByteMatchSet or an  IPSet , that specifies the web requests that you want to block or count. The ``rate-limit`` specifies the number of requests every five minutes that triggers the rule.

 

If you add more than one predicate to a ``RateBasedRule`` , a request must match all the predicates and exceed the ``rate-limit`` to be counted or blocked. For example, suppose you add the following to a ``RateBasedRule`` :

 

 
* An ``IPSet`` that matches the IP address ``192.0.2.44/32``   
 
* A ``ByteMatchSet`` that matches ``BadBot`` in the ``User-Agent`` header 
 

 

Further, you specify a ``rate-limit`` of 15,000.

 

You then add the ``RateBasedRule`` to a ``WebACL`` and specify that you want to block requests that satisfy the rule. For a request to be blocked, it must come from the IP address 192.0.2.44 *and* the ``User-Agent`` header in the request must contain the value ``BadBot`` . Further, requests that match these two conditions much be received at a rate of more than 15,000 every five minutes. If the rate drops below this limit, AWS WAF no longer blocks the requests.

 

As a second example, suppose you want to limit requests to a particular page on your site. To do this, you could add the following to a ``RateBasedRule`` :

 

 
* A ``ByteMatchSet`` with ``FieldToMatch`` of ``URI``   
 
* A ``PositionalConstraint`` of ``STARTS_WITH``   
 
* A ``TargetString`` of ``login``   
 

 

Further, you specify a ``rate-limit`` of 15,000.

 

By adding this ``RateBasedRule`` to a ``WebACL`` , you could limit requests to your login page without affecting the rest of your site.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-2015-08-24/UpdateRateBasedRule>`_


========
Synopsis
========

::

    update-rate-based-rule
  --rule-id <value>
  --change-token <value>
  --updates <value>
  --rate-limit <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-id`` (string)


  The ``RuleId`` of the ``RateBasedRule`` that you want to update. ``RuleId`` is returned by ``create-rate-based-rule`` and by  list-rate-based-rules .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--updates`` (list)


  An array of ``RuleUpdate`` objects that you want to insert into or delete from a  RateBasedRule . 

  



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



``--rate-limit`` (long)


  The maximum number of requests, which have an identical value in the field specified by the ``RateKey`` , allowed in a five-minute period. If the number of requests exceeds the ``rate-limit`` and the other predicates specified in the rule are also met, AWS WAF triggers the action that is specified for this rule.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``update-rate-based-rule`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

