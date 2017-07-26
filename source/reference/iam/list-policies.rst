[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-policies:


*************
list-policies
*************



===========
Description
===========



Lists all the managed policies that are available to your account, including your own customer managed policies and all AWS managed policies. 

 

You can filter the list of policies that is returned using the optional ``OnlyAttached`` , ``Scope`` , and ``PathPrefix`` parameters. For example, to list only the customer managed policies in your AWS account, set ``Scope`` to ``Local`` . To list only AWS managed policies, set ``Scope`` to ``AWS`` . 

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 

 

For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



``list-policies`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Policies``


========
Synopsis
========

::

    list-policies
  [--scope <value>]
  [--only-attached | --no-only-attached]
  [--path-prefix <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--scope`` (string)


  The scope to use for filtering the results. 

   

  To list only AWS managed policies, set ``Scope`` to ``AWS`` . To list only the customer managed policies in your AWS account, set ``Scope`` to ``Local`` . 

   

  This parameter is optional. If it is not included, or if it is set to ``All`` , all policies are returned.

  

  Possible values:

  
  *   ``All``

  
  *   ``AWS``

  
  *   ``Local``

  

  

``--only-attached`` | ``--no-only-attached`` (boolean)


  A flag to filter the results to only the attached policies. 

   

  When ``OnlyAttached`` is ``true`` , the returned list contains only the policies that are attached to a user, group, or role. When ``OnlyAttached`` is ``false`` , or when the parameter is not included, all policies are returned.

  

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

**To list managed policies that are available to your AWS account**

This example returns a collection of the first two managed policies available in the current AWS account::

  aws iam list-policies --max-items 2

Output::

  {
      "Marker": "AAIWFnoA2MQ9zN9nnTorukxr1uesDIDa4u+q1mEfaurCDZ1AuCYagYfayKYGvu75BEGk8PooPsw5uvumkuizFACZ8f4rKtN1RuBWiVDBWet2OA==",
	  "IsTruncated": true,
	  "Policies": [
	  {
		  "PolicyName": "AdministratorAccess",
		  "CreateDate": "2015-02-06T18:39:46Z",
		  "AttachmentCount": 5,
		  "IsAttachable": true,
		  "PolicyId": "ANPAIWMBCKSKIEE64ZLYK",
		  "DefaultVersionId": "v1",
		  "Path": "/",
		  "Arn": "arn:aws:iam::aws:policy/AdministratorAccess",
		  "UpdateDate": "2015-02-06T18:39:46Z"
		},
		{
		  "PolicyName": "ASamplePolicy",
          "CreateDate": "2015-06-17T19:23;32Z",
          "AttachmentCount": "0",
          "IsAttachable": "true",
		  "PolicyId": "Z27SI6FQMGNQ2EXAMPLE1",
          "DefaultVersionId": "v1",
		  "Path": "/",
		  "Arn": "arn:aws:iam::123456789012:policy/ASamplePolicy",
		  "UpdateDate": "2015-06-17T19:23:32Z"
		}
	  ]
  }

For more information, see `Overview of IAM Policies`_ in the *Using IAM* guide.

.. _`Overview of IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html

======
Output
======

Policies -> (list)

  

  A list of policies.

  

  (structure)

    

    Contains information about a managed policy.

     

    This data type is used as a response element in the  create-policy ,  get-policy , and  list-policies actions. 

     

    For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

    

    PolicyName -> (string)

      

      The friendly name (not ARN) identifying the policy.

      

      

    PolicyId -> (string)

      

      The stable and unique string identifying the policy. 

       

      For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources. 

       

      For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

      

      

    Path -> (string)

      

      The path to the policy.

       

      For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

      

      

    DefaultVersionId -> (string)

      

      The identifier for the version of the policy that is set as the default version. 

      

      

    AttachmentCount -> (integer)

      

      The number of entities (users, groups, and roles) that the policy is attached to.

      

      

    IsAttachable -> (boolean)

      

      Specifies whether the policy can be attached to an IAM user, group, or role. 

      

      

    Description -> (string)

      

      A friendly description of the policy.

       

      This element is included in the response to the  get-policy operation. It is not included in the response to the  list-policies operation. 

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format`_ , when the policy was created.

      

      

    UpdateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format`_ , when the policy was last updated.

       

      When a policy has only one version, this field contains the date and time when the policy was created. When a policy has more than one version, this field contains the date and time when the most recent policy version was created. 

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
