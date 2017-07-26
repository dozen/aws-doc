[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf create-rate-based-rule:


**********************
create-rate-based-rule
**********************



===========
Description
===========



Creates a  RateBasedRule . The ``RateBasedRule`` contains a ``rate-limit`` , which specifies the maximum number of requests that AWS WAF allows from a specified IP address in a five-minute period. The ``RateBasedRule`` also contains the ``IPSet`` objects, ``ByteMatchSet`` objects, and other predicates that identify the requests that you want to count or block if these requests exceed the ``rate-limit`` .

 

If you add more than one predicate to a ``RateBasedRule`` , a request not only must exceed the ``rate-limit`` , but it also must match all the specifications to be counted or blocked. For example, suppose you add the following to a ``RateBasedRule`` :

 

 
* An ``IPSet`` that matches the IP address ``192.0.2.44/32``   
 
* A ``ByteMatchSet`` that matches ``BadBot`` in the ``User-Agent`` header 
 

 

Further, you specify a ``rate-limit`` of 15,000.

 

You then add the ``RateBasedRule`` to a ``WebACL`` and specify that you want to block requests that meet the conditions in the rule. For a request to be blocked, it must come from the IP address 192.0.2.44 *and* the ``User-Agent`` header in the request must contain the value ``BadBot`` . Further, requests that match these two conditions must be received at a rate of more than 15,000 requests every five minutes. If both conditions are met and the rate is exceeded, AWS WAF blocks the requests. If the rate drops below 15,000 for a five-minute period, AWS WAF no longer blocks the requests.

 

As a second example, suppose you want to limit requests to a particular page on your site. To do this, you could add the following to a ``RateBasedRule`` :

 

 
* A ``ByteMatchSet`` with ``FieldToMatch`` of ``URI``   
 
* A ``PositionalConstraint`` of ``STARTS_WITH``   
 
* A ``TargetString`` of ``login``   
 

 

Further, you specify a ``rate-limit`` of 15,000.

 

By adding this ``RateBasedRule`` to a ``WebACL`` , you could limit requests to your login page without affecting the rest of your site.

 

To create and configure a ``RateBasedRule`` , perform the following steps:

 

 
* Create and update the predicates that you want to include in the rule. For more information, see  create-byte-match-set ,  create-ip-set , and  create-sql-injection-match-set . 
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``create-rule`` request. 
 
* Submit a ``create-rate-based-rule`` request. 
 
* Use ``get-change-token`` to get the change token that you provide in the ``change-token`` parameter of an  update-rule request. 
 
* Submit an ``update-rate-based-rule`` request to specify the predicates that you want to include in the rule. 
 
* Create and update a ``WebACL`` that contains the ``RateBasedRule`` . For more information, see  create-web-acl . 
 

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide <http://docs.aws.amazon.com/waf/latest/developerguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-2015-08-24/CreateRateBasedRule>`_


========
Synopsis
========

::

    create-rate-based-rule
  --name <value>
  --metric-name <value>
  --rate-key <value>
  --rate-limit <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  A friendly name or description of the  RateBasedRule . You can't change the name of a ``RateBasedRule`` after you create it.

  

``--metric-name`` (string)


  A friendly name or description for the metrics for this ``RateBasedRule`` . The name can contain only alphanumeric characters (A-Z, a-z, 0-9); the name can't contain whitespace. You can't change the name of the metric after you create the ``RateBasedRule`` .

  

``--rate-key`` (string)


  The field that AWS WAF uses to determine if requests are likely arriving from a single source and thus subject to rate monitoring. The only valid value for ``rate-key`` is ``IP`` . ``IP`` indicates that requests that arrive from the same IP address are subject to the ``rate-limit`` that is specified in the ``RateBasedRule`` .

  

  Possible values:

  
  *   ``IP``

  

  

``--rate-limit`` (long)


  The maximum number of requests, which have an identical value in the field that is specified by ``rate-key`` , allowed in a five-minute period. If the number of requests exceeds the ``rate-limit`` and the other predicates specified in the rule are also met, AWS WAF triggers the action that is specified for this rule.

  

``--change-token`` (string)


  The ``change-token`` that you used to submit the ``create-rate-based-rule`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Rule -> (structure)

  

  The  RateBasedRule that is returned in the ``create-rate-based-rule`` response.

  

  RuleId -> (string)

    

    A unique identifier for a ``RateBasedRule`` . You use ``RuleId`` to get more information about a ``RateBasedRule`` (see  get-rate-based-rule ), update a ``RateBasedRule`` (see  update-rate-based-rule ), insert a ``RateBasedRule`` into a ``WebACL`` or delete one from a ``WebACL`` (see  update-web-acl ), or delete a ``RateBasedRule`` from AWS WAF (see  delete-rate-based-rule ).

    

    

  Name -> (string)

    

    A friendly name or description for a ``RateBasedRule`` . You can't change the name of a ``RateBasedRule`` after you create it.

    

    

  MetricName -> (string)

    

    A friendly name or description for the metrics for a ``RateBasedRule`` . The name can contain only alphanumeric characters (A-Z, a-z, 0-9); the name can't contain whitespace. You can't change the name of the metric after you create the ``RateBasedRule`` .

    

    

  MatchPredicates -> (list)

    

    The ``Predicates`` object contains one ``Predicate`` element for each  ByteMatchSet ,  IPSet , or  SqlInjectionMatchSet object that you want to include in a ``RateBasedRule`` .

    

    (structure)

      

      Specifies the  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , and  SizeConstraintSet objects that you want to add to a ``Rule`` and, for each object, indicates whether you want to negate the settings, for example, requests that do NOT originate from the IP address 192.0.2.44. 

      

      Negated -> (boolean)

        

        Set ``Negated`` to ``False`` if you want AWS WAF to allow, block, or count requests based on the settings in the specified  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , or  SizeConstraintSet . For example, if an ``IPSet`` includes the IP address ``192.0.2.44`` , AWS WAF will allow or block requests based on that IP address.

         

        Set ``Negated`` to ``True`` if you want AWS WAF to allow or block a request based on the negation of the settings in the  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , or  SizeConstraintSet . For example, if an ``IPSet`` includes the IP address ``192.0.2.44`` , AWS WAF will allow, block, or count requests based on all IP addresses *except*  ``192.0.2.44`` .

        

        

      Type -> (string)

        

        The type of predicate in a ``Rule`` , such as ``ByteMatchSet`` or ``IPSet`` .

        

        

      DataId -> (string)

        

        A unique identifier for a predicate in a ``Rule`` , such as ``ByteMatchSetId`` or ``IPSetId`` . The ID is returned by the corresponding ``Create`` or ``List`` command.

        

        

      

    

  RateKey -> (string)

    

    The field that AWS WAF uses to determine if requests are likely arriving from single source and thus subject to rate monitoring. The only valid value for ``rate-key`` is ``IP`` . ``IP`` indicates that requests arriving from the same IP address are subject to the ``rate-limit`` that is specified in the ``RateBasedRule`` .

    

    

  RateLimit -> (long)

    

    The maximum number of requests, which have an identical value in the field specified by the ``rate-key`` , allowed in a five-minute period. If the number of requests exceeds the ``rate-limit`` and the other predicates specified in the rule are also met, AWS WAF triggers the action that is specified for this rule.

    

    

  

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``create-rate-based-rule`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

