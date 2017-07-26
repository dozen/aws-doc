[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-role-policy:


******************
delete-role-policy
******************



===========
Description
===========



Deletes the specified inline policy that is embedded in the specified role.

 

A role can also have managed policies attached to it. To detach a managed policy from a role, use  detach-role-policy . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    delete-role-policy
  --role-name <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--role-name`` (string)


  The name (friendly name, not ARN) identifying the role that the policy is embedded in.

  

``--policy-name`` (string)


  The name identifying the policy document to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To remove a policy from an IAM role**

The following ``delete-role-policy`` command removes the policy named ``ExamplePolicy`` from the role named ``Test-Role``::

  aws iam delete-role-policy --role-name Test-Role --policy-name ExamplePolicy

For more information, see `Creating a Role`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html



======
Output
======

None

.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
