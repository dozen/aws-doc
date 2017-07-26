[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-attached-user-policies:


***************************
list-attached-user-policies
***************************



===========
Description
===========



Lists all managed policies that are attached to the specified user. 

 

A user can also have inline policies embedded with it. To list the inline policies for a user, use the  list-user-policies API. For information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. You can use the ``PathPrefix`` parameter to limit the list of policies to only those matching the specified path prefix. If there are no policies attached to the specified group (or none that match the specified path prefix), the action returns an empty list. 



``list-attached-user-policies`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``AttachedPolicies``


========
Synopsis
========

::

    list-attached-user-policies
  --user-name <value>
  [--path-prefix <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name (friendly name, not ARN) of the user to list attached policies for.

  

``--path-prefix`` (string)


  The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all policies.

  

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

**To list all managed policies that are attached to the specified user**

This command returns the names and ARNs of the managed policies for the IAM user named ``Bob`` in the AWS account::

  aws iam list-attached-user-policies --user-name Bob

Output::

  {
    "AttachedPolicies": [
      {
        "PolicyName": "AdministratorAccess",
        "PolicyArn": "arn:aws:iam::aws:policy/AdministratorAccess"
      },
      {
        "PolicyName": "SecurityAudit",
        "PolicyArn": "arn:aws:iam::aws:policy/SecurityAudit"
      }
    ],
    "IsTruncated": false
  }

For more information, see `Overview of IAM Policies`_ in the *Using IAM* guide.

.. _`Overview of IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html

======
Output
======

AttachedPolicies -> (list)

  

  A list of the attached policies.

  

  (structure)

    

    Contains information about an attached policy.

     

    An attached policy is a managed policy that has been attached to a user, group, or role. This data type is used as a response element in the  list-attached-group-policies ,  list-attached-role-policies ,  list-attached-user-policies , and  get-account-authorization-details actions. 

     

    For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

    

    PolicyName -> (string)

      

      The friendly name of the attached policy.

      

      

    PolicyArn -> (string)

      

      The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources. 

       

      For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
