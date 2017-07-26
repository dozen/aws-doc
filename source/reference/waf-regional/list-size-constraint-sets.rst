[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional list-size-constraint-sets:


*************************
list-size-constraint-sets
*************************



===========
Description
===========



Returns an array of  SizeConstraintSetSummary objects.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/ListSizeConstraintSets>`_


========
Synopsis
========

::

    list-size-constraint-sets
  [--next-marker <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-marker`` (string)


  If you specify a value for ``Limit`` and you have more ``SizeConstraintSets`` than the value of ``Limit`` , AWS WAF returns a ``next-marker`` value in the response that allows you to list another group of ``SizeConstraintSets`` . For the second and subsequent ``list-size-constraint-sets`` requests, specify the value of ``next-marker`` from the previous response to get information about another batch of ``SizeConstraintSets`` .

  

``--limit`` (integer)


  Specifies the number of ``SizeConstraintSet`` objects that you want AWS WAF to return for this request. If you have more ``SizeConstraintSets`` objects than the number you specify for ``Limit`` , the response includes a ``next-marker`` value that you can use to get another batch of ``SizeConstraintSet`` objects.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextMarker -> (string)

  

  If you have more ``SizeConstraintSet`` objects than the number that you specified for ``Limit`` in the request, the response includes a ``next-marker`` value. To list more ``SizeConstraintSet`` objects, submit another ``list-size-constraint-sets`` request, and specify the ``next-marker`` value from the response in the ``next-marker`` value in the next request.

  

  

SizeConstraintSets -> (list)

  

  An array of  SizeConstraintSetSummary objects.

  

  (structure)

    

    The ``Id`` and ``Name`` of a ``SizeConstraintSet`` .

    

    SizeConstraintSetId -> (string)

      

      A unique identifier for a ``SizeConstraintSet`` . You use ``SizeConstraintSetId`` to get information about a ``SizeConstraintSet`` (see  get-size-constraint-set ), update a ``SizeConstraintSet`` (see  update-size-constraint-set ), insert a ``SizeConstraintSet`` into a ``Rule`` or delete one from a ``Rule`` (see  update-rule ), and delete a ``SizeConstraintSet`` from AWS WAF (see  delete-size-constraint-set ).

       

       ``SizeConstraintSetId`` is returned by  create-size-constraint-set and by  list-size-constraint-sets .

      

      

    Name -> (string)

      

      The name of the ``SizeConstraintSet`` , if any.

      

      

    

  

