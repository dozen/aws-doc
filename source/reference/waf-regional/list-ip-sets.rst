[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional list-ip-sets:


************
list-ip-sets
************



===========
Description
===========



Returns an array of  IPSetSummary objects in the response.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/ListIPSets>`_


========
Synopsis
========

::

    list-ip-sets
  [--next-marker <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-marker`` (string)


  If you specify a value for ``Limit`` and you have more ``IPSets`` than the value of ``Limit`` , AWS WAF returns a ``next-marker`` value in the response that allows you to list another group of ``IPSets`` . For the second and subsequent ``list-ip-sets`` requests, specify the value of ``next-marker`` from the previous response to get information about another batch of ``ByteMatchSets`` .

  

``--limit`` (integer)


  Specifies the number of ``IPSet`` objects that you want AWS WAF to return for this request. If you have more ``IPSet`` objects than the number you specify for ``Limit`` , the response includes a ``next-marker`` value that you can use to get another batch of ``IPSet`` objects.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextMarker -> (string)

  

  If you have more ``IPSet`` objects than the number that you specified for ``Limit`` in the request, the response includes a ``next-marker`` value. To list more ``IPSet`` objects, submit another ``list-ip-sets`` request, and specify the ``next-marker`` value from the response in the ``next-marker`` value in the next request.

  

  

IPSets -> (list)

  

  An array of  IPSetSummary objects.

  

  (structure)

    

    Contains the identifier and the name of the ``IPSet`` .

    

    IPSetId -> (string)

      

      The ``IPSetId`` for an  IPSet . You can use ``IPSetId`` in a  get-ip-set request to get detailed information about an  IPSet .

      

      

    Name -> (string)

      

      A friendly name or description of the  IPSet . You can't change the name of an ``IPSet`` after you create it.

      

      

    

  

