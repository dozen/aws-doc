[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf get-rate-based-rule:


*******************
get-rate-based-rule
*******************



===========
Description
===========



Returns the  RateBasedRule that is specified by the ``RuleId`` that you included in the ``get-rate-based-rule`` request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-2015-08-24/GetRateBasedRule>`_


========
Synopsis
========

::

    get-rate-based-rule
  --rule-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-id`` (string)


  The ``RuleId`` of the  RateBasedRule that you want to get. ``RuleId`` is returned by  create-rate-based-rule and by  list-rate-based-rules .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Rule -> (structure)

  

  Information about the  RateBasedRule that you specified in the ``get-rate-based-rule`` request.

  

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

    

    The field that AWS WAF uses to determine if requests are likely arriving from single source and thus subject to rate monitoring. The only valid value for ``RateKey`` is ``IP`` . ``IP`` indicates that requests arriving from the same IP address are subject to the ``RateLimit`` that is specified in the ``RateBasedRule`` .

    

    

  RateLimit -> (long)

    

    The maximum number of requests, which have an identical value in the field specified by the ``RateKey`` , allowed in a five-minute period. If the number of requests exceeds the ``RateLimit`` and the other predicates specified in the rule are also met, AWS WAF triggers the action that is specified for this rule.

    

    

  

