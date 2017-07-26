[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam attach-group-policy:


*******************
attach-group-policy
*******************



===========
Description
===========



Attaches the specified managed policy to the specified group.

 

You use this API to attach a managed policy to a group. To embed an inline policy in a group, use  put-group-policy . 

 

For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    attach-group-policy
  --group-name <value>
  --policy-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--group-name`` (string)


  The name (friendly name, not ARN) of the group to attach the policy to.

  

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

**To attach a managed policy to an IAM group**

The following ``attach-group-policy`` command attaches the AWS managed policy named ``ReadOnlyAccess`` to the IAM group named ``Finance``::

  aws iam attach-group-policy --policy-arn arn:aws:iam::aws:policy/ReadOnlyAccess --group-name Finance

For more information, see `Managed Policies and Inline Policies`_ in the *Using IAM* guide.

.. _`Managed Policies and Inline Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html

======
Output
======

None

.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
