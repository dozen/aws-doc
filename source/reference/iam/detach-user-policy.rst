[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam detach-user-policy:


******************
detach-user-policy
******************



===========
Description
===========



Removes the specified managed policy from the specified user. 

 

A user can also have inline policies embedded with it. To delete an inline policy, use the  delete-user-policy API. For information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    detach-user-policy
  --user-name <value>
  --policy-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name (friendly name, not ARN) of the user to detach the policy from.

  

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

**To detach a policy from a user**

This example removes the managed policy with the ARN ``arn:aws:iam::123456789012:policy/TesterPolicy`` from the user ``Bob``::

  aws iam detach-user-policy --user-name Bob --policy-arn arn:aws:iam::123456789012:policy/TesterPolicy 


For more information, see `Overview of IAM Policies`_ in the *Using IAM* guide.

.. _`Overview of IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html

======
Output
======

None

.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
