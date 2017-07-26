[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional list-xss-match-sets:


*******************
list-xss-match-sets
*******************



===========
Description
===========



Returns an array of  XssMatchSet objects.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/ListXssMatchSets>`_


========
Synopsis
========

::

    list-xss-match-sets
  [--next-marker <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-marker`` (string)


  If you specify a value for ``Limit`` and you have more  XssMatchSet objects than the value of ``Limit`` , AWS WAF returns a ``next-marker`` value in the response that allows you to list another group of ``XssMatchSets`` . For the second and subsequent ``list-xss-match-sets`` requests, specify the value of ``next-marker`` from the previous response to get information about another batch of ``XssMatchSets`` .

  

``--limit`` (integer)


  Specifies the number of  XssMatchSet objects that you want AWS WAF to return for this request. If you have more ``XssMatchSet`` objects than the number you specify for ``Limit`` , the response includes a ``next-marker`` value that you can use to get another batch of ``Rules`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextMarker -> (string)

  

  If you have more  XssMatchSet objects than the number that you specified for ``Limit`` in the request, the response includes a ``next-marker`` value. To list more ``XssMatchSet`` objects, submit another ``list-xss-match-sets`` request, and specify the ``next-marker`` value from the response in the ``next-marker`` value in the next request.

  

  

XssMatchSets -> (list)

  

  An array of  XssMatchSetSummary objects.

  

  (structure)

    

    The ``Id`` and ``Name`` of an ``XssMatchSet`` .

    

    XssMatchSetId -> (string)

      

      A unique identifier for an ``XssMatchSet`` . You use ``XssMatchSetId`` to get information about a ``XssMatchSet`` (see  get-xss-match-set ), update an ``XssMatchSet`` (see  update-xss-match-set ), insert an ``XssMatchSet`` into a ``Rule`` or delete one from a ``Rule`` (see  update-rule ), and delete an ``XssMatchSet`` from AWS WAF (see  delete-xss-match-set ).

       

       ``XssMatchSetId`` is returned by  create-xss-match-set and by  list-xss-match-sets .

      

      

    Name -> (string)

      

      The name of the ``XssMatchSet`` , if any, specified by ``Id`` .

      

      

    

  

