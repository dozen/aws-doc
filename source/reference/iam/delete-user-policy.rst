[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-user-policy:


******************
delete-user-policy
******************



===========
Description
===========



Deletes the specified inline policy that is embedded in the specified user.

 

A user can also have managed policies attached to it. To detach a managed policy from a user, use  detach-user-policy . For more information about policies, refer to `Managed Policies and Inline Policies`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    delete-user-policy
  --user-name <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name (friendly name, not ARN) identifying the user that the policy is embedded in.

  

``--policy-name`` (string)


  The name identifying the policy document to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To remove a policy from an IAM user**

The following ``delete-user-policy`` command removes the specified policy from the IAM user named ``Bob``::

  aws iam delete-user-policy --user-name Bob --policy-name ExamplePolicy

To get a list of policies for an IAM user, use the ``list-user-policies`` command.

For more information, see `Adding a New User to Your AWS Account`_ in the *Using IAM* guide.

.. _`Adding a New User to Your AWS Account`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_SettingUpUser.html







======
Output
======

None

.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
