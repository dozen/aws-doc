[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf list-byte-match-sets:


********************
list-byte-match-sets
********************



===========
Description
===========



Returns an array of  ByteMatchSetSummary objects.



========
Synopsis
========

::

    list-byte-match-sets
  [--next-marker <value>]
  --limit <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--next-marker`` (string)


  If you specify a value for ``Limit`` and you have more ``ByteMatchSets`` than the value of ``Limit`` , AWS WAF returns a ``next-marker`` value in the response that allows you to list another group of ``ByteMatchSets`` . For the second and subsequent ``list-byte-match-sets`` requests, specify the value of ``next-marker`` from the previous response to get information about another batch of ``ByteMatchSets`` .

  

``--limit`` (integer)


  Specifies the number of ``ByteMatchSet`` objects that you want AWS WAF to return for this request. If you have more ``ByteMatchSets`` objects than the number you specify for ``Limit`` , the response includes a ``next-marker`` value that you can use to get another batch of ``ByteMatchSet`` objects.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

NextMarker -> (string)

  

  If you have more ``ByteMatchSet`` objects than the number that you specified for ``Limit`` in the request, the response includes a ``next-marker`` value. To list more ``ByteMatchSet`` objects, submit another ``list-byte-match-sets`` request, and specify the ``next-marker`` value from the response in the ``next-marker`` value in the next request.

  

  

ByteMatchSets -> (list)

  

  An array of  ByteMatchSetSummary objects.

  

  (structure)

    

    Returned by  list-byte-match-sets . Each ``ByteMatchSetSummary`` object includes the ``Name`` and ``ByteMatchSetId`` for one  ByteMatchSet .

    

    ByteMatchSetId -> (string)

      

      The ``ByteMatchSetId`` for a ``ByteMatchSet`` . You use ``ByteMatchSetId`` to get information about a ``ByteMatchSet`` , update a ``ByteMatchSet`` , remove a ``ByteMatchSet`` from a ``Rule`` , and delete a ``ByteMatchSet`` from AWS WAF.

       

      ``ByteMatchSetId`` is returned by  create-byte-match-set and by  list-byte-match-sets .

      

      

    Name -> (string)

      

      A friendly name or description of the  ByteMatchSet . You can't change ``Name`` after you create a ``ByteMatchSet`` .

      

      

    

  

