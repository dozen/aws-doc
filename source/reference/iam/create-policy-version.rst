[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-policy-version:


*********************
create-policy-version
*********************



===========
Description
===========



Creates a new version of the specified managed policy. To update a managed policy, you create a new policy version. A managed policy can have up to five versions. If the policy has five versions, you must delete an existing version using  delete-policy-version before you create a new version. 

 

Optionally, you can set the new version as the policy's default version. The default version is the operative version; that is, the version that is in effect for the IAM users, groups, and roles that the policy is attached to. 

 

For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    create-policy-version
  --policy-arn <value>
  --policy-document <value>
  [--set-as-default | --no-set-as-default]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-arn`` (string)


  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources. 

   

  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

  

``--policy-document`` (string)


  The policy document.

  

``--set-as-default`` | ``--no-set-as-default`` (boolean)


  Specifies whether to set this version as the policy's default version.

   

  When this parameter is ``true`` , the new policy version becomes the operative version; that is, the version that is in effect for the IAM users, groups, and roles that the policy is attached to.

   

  For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a new version of a managed policy**


This example creates a new ``v2`` version of the IAM policy whose ARN is ``arn:aws:iam::123456789012:policy/MyPolicy`` and makes it the default version::


  aws iam create-policy-version --policy-arn arn:aws:iam::123456789012:policy/MyPolicy --policy-document file://NewPolicyVersion.json --set-as-default

Output::

  {
      "PolicyVersion": {
          "CreateDate": "2015-06-16T18:56:03.721Z",
          "VersionId": "v2",
          "IsDefaultVersion": true
      }
  }

For more information, see `Versioning for Managed Policies`_ in the *Using IAM* guide.

.. _`Versioning for Managed Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_managed-versioning.html

======
Output
======

PolicyVersion -> (structure)

  

  Information about the policy version.

  

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

    

    

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Versioning for Managed Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-versions.html
.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
