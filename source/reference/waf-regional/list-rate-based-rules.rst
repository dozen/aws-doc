[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional list-rate-based-rules:


*********************
list-rate-based-rules
*********************



===========
Description
===========



Returns an array of  RuleSummary objects.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/ListRateBasedRules>`_


========
Synopsis
========

::

    list-rate-based-rules
  [--next-marker <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-marker`` (string)


  If you specify a value for ``Limit`` and you have more ``Rules`` than the value of ``Limit`` , AWS WAF returns a ``next-marker`` value in the response that allows you to list another group of ``Rules`` . For the second and subsequent ``list-rate-based-rules`` requests, specify the value of ``next-marker`` from the previous response to get information about another batch of ``Rules`` .

  

``--limit`` (integer)


  Specifies the number of ``Rules`` that you want AWS WAF to return for this request. If you have more ``Rules`` than the number that you specify for ``Limit`` , the response includes a ``next-marker`` value that you can use to get another batch of ``Rules`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextMarker -> (string)

  

  If you have more ``Rules`` than the number that you specified for ``Limit`` in the request, the response includes a ``next-marker`` value. To list more ``Rules`` , submit another ``list-rate-based-rules`` request, and specify the ``next-marker`` value from the response in the ``next-marker`` value in the next request.

  

  

Rules -> (list)

  

  An array of  RuleSummary objects.

  

  (structure)

    

    Contains the identifier and the friendly name or description of the ``Rule`` .

    

    RuleId -> (string)

      

      A unique identifier for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  get-rule ), update a ``Rule`` (see  update-rule ), insert a ``Rule`` into a ``WebACL`` or delete one from a ``WebACL`` (see  update-web-acl ), or delete a ``Rule`` from AWS WAF (see  delete-rule ).

       

       ``RuleId`` is returned by  create-rule and by  list-rules .

      

      

    Name -> (string)

      

      A friendly name or description of the  Rule . You can't change the name of a ``Rule`` after you create it.

      

      

    

  

