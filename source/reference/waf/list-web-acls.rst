[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf list-web-acls:


*************
list-web-acls
*************



===========
Description
===========



Returns an array of  WebACLSummary objects in the response.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-2015-08-24/ListWebACLs>`_


``list-web-acls`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``WebACLs``


========
Synopsis
========

::

    list-web-acls
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

  

  If you have more ``WebACL`` objects than the number that you specified for ``Limit`` in the request, the response includes a ``next-marker`` value. To list more ``WebACL`` objects, submit another ``list-web-acls`` request, and specify the ``next-marker`` value from the response in the ``next-marker`` value in the next request.

  

  

WebACLs -> (list)

  

  An array of  WebACLSummary objects.

  

  (structure)

    

    Contains the identifier and the name or description of the  WebACL .

    

    WebACLId -> (string)

      

      A unique identifier for a ``WebACL`` . You use ``WebACLId`` to get information about a ``WebACL`` (see  get-web-acl ), update a ``WebACL`` (see  update-web-acl ), and delete a ``WebACL`` from AWS WAF (see  delete-web-acl ).

       

       ``WebACLId`` is returned by  create-web-acl and by  list-web-acls .

      

      

    Name -> (string)

      

      A friendly name or description of the  WebACL . You can't change the name of a ``WebACL`` after you create it.

      

      

    

  

