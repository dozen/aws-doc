[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf list-byte-match-sets:


********************
list-byte-match-sets
********************



===========
Description
===========



Returns an array of  ByteMatchSetSummary objects.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-2015-08-24/ListByteMatchSets>`_


``list-byte-match-sets`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ByteMatchSets``


========
Synopsis
========

::

    list-byte-match-sets
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    

  

