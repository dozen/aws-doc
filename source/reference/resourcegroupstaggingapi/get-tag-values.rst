[ :ref:`aws <cli:aws>` . :ref:`resourcegroupstaggingapi <cli:aws resourcegroupstaggingapi>` ]

.. _cli:aws resourcegroupstaggingapi get-tag-values:


**************
get-tag-values
**************



===========
Description
===========



Returns all tag values for the specified key in the specified region for the AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/resourcegroupstaggingapi-2017-01-26/GetTagValues>`_


``get-tag-values`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``TagValues``


========
Synopsis
========

::

    get-tag-values
  --key <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key`` (string)


  The key for which you want to list all existing values in the specified region for the AWS account.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PaginationToken -> (string)

  

  A string that indicates that the response contains more data than can be returned in a single response. To receive additional data, specify this string for the ``pagination-token`` value in a subsequent request.

  

  

TagValues -> (list)

  

  A list of all tag values for the specified key in the AWS account.

  

  (string)

    

    

  

