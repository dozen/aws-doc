[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf list-rules:


**********
list-rules
**********



===========
Description
===========



Returns an array of  RuleSummary objects.



========
Synopsis
========

::

    list-rules
  [--next-marker <value>]
  --limit <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--next-marker`` (string)


  If you specify a value for ``Limit`` and you have more ``Rules`` than the value of ``Limit`` , AWS WAF returns a ``next-marker`` value in the response that allows you to list another group of ``Rules`` . For the second and subsequent ``list-rules`` requests, specify the value of ``next-marker`` from the previous response to get information about another batch of ``Rules`` .

  

``--limit`` (integer)


  Specifies the number of ``Rules`` that you want AWS WAF to return for this request. If you have more ``Rules`` than the number that you specify for ``Limit`` , the response includes a ``next-marker`` value that you can use to get another batch of ``Rules`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

NextMarker -> (string)

  

  If you have more ``Rules`` than the number that you specified for ``Limit`` in the request, the response includes a ``next-marker`` value. To list more ``Rules`` , submit another ``list-rules`` request, and specify the ``next-marker`` value from the response in the ``next-marker`` value in the next request.

  

  

Rules -> (list)

  

  An array of  RuleSummary objects.

  

  (structure)

    

    Contains the identifier and the friendly name or description of the ``Rule`` .

    

    RuleId -> (string)

      

      A unique identifier for a ``Rule`` . You use ``RuleId`` to get more information about a ``Rule`` (see  get-rule ), update a ``Rule`` (see  update-rule ), insert a ``Rule`` into a ``WebACL`` or delete one from a ``WebACL`` (see  update-web-acl ), or delete a ``Rule`` from AWS WAF (see  delete-rule ).

       

      ``RuleId`` is returned by  create-rule and by  list-rules .

      

      

    Name -> (string)

      

      A friendly name or description of the  Rule . You can't change the name of a ``Rule`` after you create it.

      

      

    

  
