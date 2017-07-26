[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf list-xss-match-sets:


*******************
list-xss-match-sets
*******************



===========
Description
===========



Returns an array of  XssMatchSet objects.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-2015-08-24/ListXssMatchSets>`_


``list-xss-match-sets`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``XssMatchSets``


========
Synopsis
========

::

    list-xss-match-sets
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

      

      

    

  

