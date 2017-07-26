[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf get-rule:


********
get-rule
********



===========
Description
===========



Returns the  Rule that is specified by the ``RuleId`` that you included in the ``get-rule`` request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-2015-08-24/GetRule>`_


========
Synopsis
========

::

    get-rule
  --rule-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-id`` (string)


  The ``RuleId`` of the  Rule that you want to get. ``RuleId`` is returned by  create-rule and by  list-rules .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Rule -> (structure)

  

  Information about the  Rule that you specified in the ``get-rule`` request. For more information, see the following topics:

   

   
  *  Rule : Contains ``MetricName`` , ``Name`` , an array of ``Predicate`` objects, and ``RuleId``   
   
  *  Predicate : Each ``Predicate`` object contains ``DataId`` , ``Negated`` , and ``Type``   
   

  

  RuleId -> (string)

    

    A unique identifier for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  get-rule ), update a ``Rule`` (see  update-rule ), insert a ``Rule`` into a ``WebACL`` or delete a one from a ``WebACL`` (see  update-web-acl ), or delete a ``Rule`` from AWS WAF (see  delete-rule ).

     

     ``RuleId`` is returned by  create-rule and by  list-rules .

    

    

  Name -> (string)

    

    The friendly name or description for the ``Rule`` . You can't change the name of a ``Rule`` after you create it.

    

    

  MetricName -> (string)

    

    A friendly name or description for the metrics for this ``Rule`` . The name can contain only alphanumeric characters (A-Z, a-z, 0-9); the name can't contain whitespace. You can't change ``MetricName`` after you create the ``Rule`` .

    

    

  Predicates -> (list)

    

    The ``Predicates`` object contains one ``Predicate`` element for each  ByteMatchSet ,  IPSet , or  SqlInjectionMatchSet object that you want to include in a ``Rule`` .

    

    (structure)

      

      Specifies the  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , and  SizeConstraintSet objects that you want to add to a ``Rule`` and, for each object, indicates whether you want to negate the settings, for example, requests that do NOT originate from the IP address 192.0.2.44. 

      

      Negated -> (boolean)

        

        Set ``Negated`` to ``False`` if you want AWS WAF to allow, block, or count requests based on the settings in the specified  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , or  SizeConstraintSet . For example, if an ``IPSet`` includes the IP address ``192.0.2.44`` , AWS WAF will allow or block requests based on that IP address.

         

        Set ``Negated`` to ``True`` if you want AWS WAF to allow or block a request based on the negation of the settings in the  ByteMatchSet ,  IPSet ,  SqlInjectionMatchSet ,  XssMatchSet , or  SizeConstraintSet . For example, if an ``IPSet`` includes the IP address ``192.0.2.44`` , AWS WAF will allow, block, or count requests based on all IP addresses *except*  ``192.0.2.44`` .

        

        

      Type -> (string)

        

        The type of predicate in a ``Rule`` , such as ``ByteMatchSet`` or ``IPSet`` .

        

        

      DataId -> (string)

        

        A unique identifier for a predicate in a ``Rule`` , such as ``ByteMatchSetId`` or ``IPSetId`` . The ID is returned by the corresponding ``Create`` or ``List`` command.

        

        

      

    

  

