[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-account-aliases:


********************
list-account-aliases
********************



===========
Description
===========



Lists the account alias associated with the AWS account (Note: you can have only one). For information about using an AWS account alias, see `Using an Alias for Your AWS Account ID <http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/ListAccountAliases>`_


``list-account-aliases`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``AccountAliases``


========
Synopsis
========

::

    list-account-aliases
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list account aliases**

The following ``list-account-aliases`` command lists the aliases for the current account::

  aws iam list-account-aliases

Output::

  "AccountAliases": [
    "mycompany"
  ]

For more information, see `Using an Alias for Your AWS Account ID`_ in the *Using IAM* guide.

.. _`Using an Alias for Your AWS Account ID`: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html



======
Output
======

AccountAliases -> (list)

  

  A list of aliases associated with the account. AWS supports only one alias per account.

  

  (string)

    

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  

