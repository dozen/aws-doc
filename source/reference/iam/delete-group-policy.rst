[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-group-policy:


*******************
delete-group-policy
*******************



===========
Description
===========



Deletes the specified inline policy that is embedded in the specified group.

 

A group can also have managed policies attached to it. To detach a managed policy from a group, use  detach-group-policy . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    delete-group-policy
  --group-name <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--group-name`` (string)


  The name (friendly name, not ARN) identifying the group that the policy is embedded in.

  

``--policy-name`` (string)


  The name identifying the policy document to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a policy from an IAM group**

The following ``delete-group-policy`` command deletes the policy named ``ExamplePolicy`` from the group named ``Admins``::

  aws iam delete-group-policy --group-name Admins --policy-name ExamplePolicy

To see the policies attached to a group, use the ``list-group-policies`` command.

For more information, see `Managing IAM Policies`_ in the *Using IAM* guide.

.. _`Managing IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingPolicies.html



======
Output
======

None

.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
