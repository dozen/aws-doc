[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-policy-version:


******************
get-policy-version
******************



===========
Description
===========



Retrieves information about the specified version of the specified managed policy, including the policy document. 

 

To list the available versions for a policy, use  list-policy-versions . 

 

This API retrieves information about managed policies. To retrieve information about an inline policy that is embedded in a user, group, or role, use the  get-user-policy ,  get-group-policy , or  get-role-policy API. 

 

For more information about the types of policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    get-policy-version
  --policy-arn <value>
  --version-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-arn`` (string)


  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources. 

   

  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

  

``--version-id`` (string)


  Identifies the policy version to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To retrieve information about the specified version of the specified managed policy**

This example returns the policy document for the v2 version of the policy whose ARN is ``arn:aws:iam::123456789012:policy/MyManagedPolicy``::

  aws iam get-policy-version --policy-arn arn:aws:iam::123456789012:policy/MyPolicy --version-id v2


Output::

  {
      "PolicyVersion": {
          "CreateDate": "2015-06-17T19:23;32Z",
          "VersionId": "v2",
          "Document": {
			"Version": "2012-10-17",
			"Statement": [
				{
					"Action": "iam:*",
					"Resource": "*",
					"Effect": "Allow"
				}
			]
		  }
          "IsDefaultVersion": "false"
      }
  }

For more information, see `Overview of IAM Policies`_ in the *Using IAM* guide.

.. _`Overview of IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html

======
Output
======

PolicyVersion -> (structure)

  

  Information about the policy version.

   

  For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* . 

  

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

    

    

  



.. _Versioning for Managed Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-versions.html
.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
