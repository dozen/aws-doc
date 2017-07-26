[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-policy-version:


*********************
delete-policy-version
*********************



===========
Description
===========



Deletes the specified version of the specified managed policy.

 

You cannot delete the default version of a policy using this API. To delete the default version of a policy, use  delete-policy . To find out which version of a policy is marked as the default version, use  list-policy-versions . 

 

For information about versions for managed policies, refer to `Versioning for Managed Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    delete-policy-version
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


  The policy version to delete.

   

  For more information about managed policy versions, see `Versioning for Managed Policies`_ in the *IAM User Guide* . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a version of a managed policy**

This example deletes the version identified as ``v2`` from the policy whose ARN is ``arn:aws:iam::123456789012:policy/MySamplePolicy``::

  aws iam delete-policy-version --policy-arn arn:aws:iam::123456789012:policy/MyPolicy --version-id v2


For more information, see `Overview of IAM Policies`_ in the *Using IAM* guide.

.. _`Overview of IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html

======
Output
======

None

.. _Versioning for Managed Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-versions.html
.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
