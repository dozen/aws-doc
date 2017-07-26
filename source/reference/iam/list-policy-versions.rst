[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-policy-versions:


********************
list-policy-versions
********************



===========
Description
===========



Lists information about the versions of the specified managed policy, including the version that is set as the policy's default version. 

 

For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



``list-policy-versions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Versions``


========
Synopsis
========

::

    list-policy-versions
  --policy-arn <value>
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-arn`` (string)


  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources. 

   

  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

  

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

**To list information about the versions of the specified managed policy**

This example returns the list of available versions of the policy whose ARN is ``arn:aws:iam::123456789012:policy/MySamplePolicy``::

  aws iam list-policy-versions --policy-arn arn:aws:iam::123456789012:policy/MySamplePolicy 

Output::

  {
    "IsTruncated": false,
    "Versions": [
      {
        "CreateDate": "2015-06-02T23:19:44Z",
        "VersionId": "v2",
        "IsDefaultVersion": true
      },
      {
        "CreateDate": "2015-06-02T22:30:47Z",
        "VersionId": "v1",
        "IsDefaultVersion": false
      }
    ]
  }

For more information, see `Overview of IAM Policies`_ in the *Using IAM* guide.

.. _`Overview of IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html

======
Output
======

Versions -> (list)

  

  A list of policy versions.

   

  For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* . 

  

  (structure)

    

    Contains information about a version of a managed policy.

     

    This data type is used as a response element in the  create-policy-version ,  get-policy-version ,  list-policy-versions , and  get-account-authorization-details actions. 

     

    For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

    

    Document -> (string)

      

      The policy document.

       

      The policy document is returned in the response to the  get-policy-version and  get-account-authorization-details operations. It is not returned in the response to the  create-policy-version or  list-policy-versions operations. 

      

      

    VersionId -> (string)

      

      The identifier for the policy version.

       

      Policy version identifiers always begin with ``v`` (always lowercase). When a policy is created, the first policy version is ``v1`` . 

      

      

    IsDefaultVersion -> (boolean)

      

      Specifies whether the policy version is set as the policy's default version.

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format`_ , when the policy version was created.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _Versioning for Managed Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-versions.html
.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
