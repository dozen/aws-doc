[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-role-policy:


******************
delete-role-policy
******************



===========
Description
===========



Deletes the specified inline policy that is embedded in the specified IAM role.

 

A role can also have managed policies attached to it. To detach a managed policy from a role, use  detach-role-policy . For more information about policies, refer to `Managed Policies and Inline Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/DeleteRolePolicy>`_


========
Synopsis
========

::

    delete-role-policy
  --role-name <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-name`` (string)


  The name (friendly name, not ARN) identifying the role that the policy is embedded in.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: _+=,.@-

  

``--policy-name`` (string)


  The name of the inline policy to delete from the specified IAM role.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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