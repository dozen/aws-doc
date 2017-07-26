[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-account-aliases:


********************
list-account-aliases
********************



===========
Description
===========



Lists the account alias associated with the account (Note: you can have only one). For information about using an AWS account alias, see `Using an Alias for Your AWS Account ID`_ in the *IAM User Guide* . 



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
  [--generate-cli-skeleton]




=======
Options
=======

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  



.. _Using an Alias for Your AWS Account ID: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html
