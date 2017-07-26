[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional list-sql-injection-match-sets:


*****************************
list-sql-injection-match-sets
*****************************



===========
Description
===========



Returns an array of  SqlInjectionMatchSet objects.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/ListSqlInjectionMatchSets>`_


========
Synopsis
========

::

    list-sql-injection-match-sets
  [--next-marker <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-marker`` (string)


  If you specify a value for ``Limit`` and you have more  SqlInjectionMatchSet objects than the value of ``Limit`` , AWS WAF returns a ``next-marker`` value in the response that allows you to list another group of ``SqlInjectionMatchSets`` . For the second and subsequent ``list-sql-injection-match-sets`` requests, specify the value of ``next-marker`` from the previous response to get information about another batch of ``SqlInjectionMatchSets`` .

  

``--limit`` (integer)


  Specifies the number of  SqlInjectionMatchSet objects that you want AWS WAF to return for this request. If you have more ``SqlInjectionMatchSet`` objects than the number you specify for ``Limit`` , the response includes a ``next-marker`` value that you can use to get another batch of ``Rules`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextMarker -> (string)

  

  If you have more  SqlInjectionMatchSet objects than the number that you specified for ``Limit`` in the request, the response includes a ``next-marker`` value. To list more ``SqlInjectionMatchSet`` objects, submit another ``list-sql-injection-match-sets`` request, and specify the ``next-marker`` value from the response in the ``next-marker`` value in the next request.

  

  

SqlInjectionMatchSets -> (list)

  

  An array of  SqlInjectionMatchSetSummary objects.

  

  (structure)

    

    The ``Id`` and ``Name`` of a ``SqlInjectionMatchSet`` .

    

    SqlInjectionMatchSetId -> (string)

      

      A unique identifier for a ``SqlInjectionMatchSet`` . You use ``SqlInjectionMatchSetId`` to get information about a ``SqlInjectionMatchSet`` (see  get-sql-injection-match-set ), update a ``SqlInjectionMatchSet`` (see  update-sql-injection-match-set ), insert a ``SqlInjectionMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  update-rule ), and delete a ``SqlInjectionMatchSet`` from AWS WAF (see  delete-sql-injection-match-set ).

       

       ``SqlInjectionMatchSetId`` is returned by  create-sql-injection-match-set and by  list-sql-injection-match-sets .

      

      

    Name -> (string)

      

      The name of the ``SqlInjectionMatchSet`` , if any, specified by ``Id`` .

      

      

    

  

