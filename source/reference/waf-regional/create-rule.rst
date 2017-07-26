[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional create-rule:


***********
create-rule
***********



===========
Description
===========



Creates a ``Rule`` , which contains the ``IPSet`` objects, ``ByteMatchSet`` objects, and other predicates that identify the requests that you want to block. If you add more than one predicate to a ``Rule`` , a request must match all of the specifications to be allowed or blocked. For example, suppose you add the following to a ``Rule`` :

 

 
* An ``IPSet`` that matches the IP address ``192.0.2.44/32``   
 
* A ``ByteMatchSet`` that matches ``BadBot`` in the ``User-Agent`` header 
 

 

You then add the ``Rule`` to a ``WebACL`` and specify that you want to blocks requests that satisfy the ``Rule`` . For a request to be blocked, it must come from the IP address 192.0.2.44 *and* the ``User-Agent`` header in the request must contain the value ``BadBot`` .

 

To create and configure a ``Rule`` , perform the following steps:

 

 
* Create and update the predicates that you want to include in the ``Rule`` . For more information, see  create-byte-match-set ,  create-ip-set , and  create-sql-injection-match-set . 
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``create-rule`` request. 
 
* Submit a ``create-rule`` request. 
 
* Use ``get-change-token`` to get the change token that you provide in the ``change-token`` parameter of an  update-rule request. 
 
* Submit an ``update-rule`` request to specify the predicates that you want to include in the ``Rule`` . 
 
* Create and update a ``WebACL`` that contains the ``Rule`` . For more information, see  create-web-acl . 
 

 

For more information about how to use the AWS WAF API to allow or block HTTP requests, see the `AWS WAF Developer Guide <http://docs.aws.amazon.com/waf/latest/developerguide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/CreateRule>`_


========
Synopsis
========

::

    create-rule
  --name <value>
  --metric-name <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  A friendly name or description of the  Rule . You can't change the name of a ``Rule`` after you create it.

  

``--metric-name`` (string)


  A friendly name or description for the metrics for this ``Rule`` . The name can contain only alphanumeric characters (A-Z, a-z, 0-9); the name can't contain whitespace. You can't change the name of the metric after you create the ``Rule`` .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Rule -> (structure)

  

  The  Rule returned in the ``create-rule`` response.

  

  RuleId -> (string)

    

    A unique identifier for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  get-rule ), update a ``Rule`` (see  update-rule ), insert a ``Rule`` into a ``WebACL`` or delete a one from a ``WebACL`` (see  update-web-acl ), or delete a ``Rule`` from AWS WAF (see  delete-rule ).

     

     ``RuleId`` is returned by  create-rule and by  list-rules .

    

    

  Name -> (string)

    

    The friendly name or description for the ``Rule`` . You can't change the name of a ``Rule`` after you create it.

    

    

  MetricName -> (string)

    

    A friendly name or description for the metrics for this ``Rule`` . The name can contain only alphanumeric characters (A-Z, a-z, 0-9); the name can't contain whitespace. You can't change ``metric-name`` after you create the ``Rule`` .

    

    

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

        

        

      

    

  

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``create-rule`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

