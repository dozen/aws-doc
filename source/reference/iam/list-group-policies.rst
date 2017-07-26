[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-group-policies:


*******************
list-group-policies
*******************



===========
Description
===========



Lists the names of the inline policies that are embedded in the specified group. 

 

A group can also have managed policies attached to it. To list the managed policies that are attached to a group, use  list-attached-group-policies . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. If there are no inline policies embedded with the specified group, the action returns an empty list. 



``list-group-policies`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``PolicyNames``


========
Synopsis
========

::

    list-group-policies
  --group-name <value>
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--group-name`` (string)


  The name of the group to list policies for.

  

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

**To list all inline policies that are attached to the specified group**

The following ``list-group-policies`` command lists the names of inline policies that are attached to the IAM group named
``Admins`` in the current account::

  aws iam list-group-policies --group-name Admins

Output::

  {
      "PolicyNames": [
          "AdminRoot",
          "ExamplepPolicy"
      ]
  }

For more information, see `Managing IAM Policies`_ in the *Using IAM* guide.

.. _`Managing IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingPolicies.html



======
Output
======

PolicyNames -> (list)

  

  A list of policy names.

  

  (string)

    

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
