[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam attach-role-policy:


******************
attach-role-policy
******************



===========
Description
===========



Attaches the specified managed policy to the specified role.

 

When you attach a managed policy to a role, the managed policy is used as the role's access (permissions) policy. You cannot use a managed policy as the role's trust policy. The role's trust policy is created at the same time as the role, using  create-role . You can update a role's trust policy using  update-assume-role-policy . 

 

Use this API to attach a managed policy to a role. To embed an inline policy in a role, use  put-role-policy . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* .



========
Synopsis
========

::

    attach-role-policy
  --role-name <value>
  --policy-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--role-name`` (string)


  The name (friendly name, not ARN) of the role to attach the policy to.

  

``--policy-arn`` (string)


  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources. 

   

  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To attach a managed policy to an IAM role**

The following ``attach-role-policy`` command attaches the AWS managed policy named ``ReadOnlyAccess`` to the IAM role named ``ReadOnlyRole``::

  aws iam attach-role-policy --policy-arn arn:aws:iam::aws:policy/ReadOnlyAccess --role-name ReadOnlyRole

For more information, see `Managed Policies and Inline Policies`_ in the *Using IAM* guide.

.. _`Managed Policies and Inline Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html

======
Output
======

None

.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
