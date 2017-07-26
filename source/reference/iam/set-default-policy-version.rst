[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam set-default-policy-version:


**************************
set-default-policy-version
**************************



===========
Description
===========



Sets the specified version of the specified policy as the policy's default (operative) version. 

 

This action affects all users, groups, and roles that the policy is attached to. To list the users, groups, and roles that the policy is attached to, use the  list-entities-for-policy API. 

 

For information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    set-default-policy-version
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


  The version of the policy to set as the default (operative) version.

   

  For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To set the specified version of the specified policy as the policy's default version.**

This example sets the ``v2`` version of the policy whose ARN is ``arn:aws:iam::123456789012:policy/MyPolicy`` as the default active version::

  aws iam set-default-policy-version --policy-arn arn:aws:iam::123456789012:policy/MyPolicy --version-id v2


For more information, see `Overview of IAM Policies`_ in the *Using IAM* guide.

.. _`Overview of IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html

======
Output
======

None

.. _Versioning for Managed Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-versions.html
.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
