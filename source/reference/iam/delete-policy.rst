[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-policy:


*************
delete-policy
*************



===========
Description
===========



Deletes the specified managed policy.

 

Before you can delete a managed policy, you must detach the policy from all users, groups, and roles that it is attached to, and you must delete all of the policy's versions. The following steps describe the process for deleting a managed policy: 

 
* Detach the policy from all users, groups, and roles that the policy is attached to, using the  detach-user-policy ,  detach-group-policy , or  detach-role-policy APIs. To list all the users, groups, and roles that a policy is attached to, use  list-entities-for-policy . 
 
* Delete all versions of the policy using  delete-policy-version . To list the policy's versions, use  list-policy-versions . You cannot use  delete-policy-version to delete the version that is marked as the default version. You delete the policy's default version in the next step of the process. 
 
* Delete the policy (this automatically deletes the policy's default version) using this API. 
 

 

 

For information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    delete-policy
  --policy-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

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

**To delete an IAM policy**

This example deletes the policy whose ARN is ``arn:aws:iam::123456789012:policy/MySamplePolicy``::

  aws iam delete-policy --policy-arn arn:aws:iam::123456789012:policy/MySamplePolicy


For more information, see `Overview of IAM Policies`_ in the *Using IAM* guide.

.. _`Overview of IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html

======
Output
======

None

.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
