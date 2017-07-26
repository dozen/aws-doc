[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-assume-role-policy:


*************************
update-assume-role-policy
*************************



===========
Description
===========



Updates the policy that grants an entity permission to assume a role. For more information about roles, go to `Using Roles to Delegate Permissions and Federate Identities`_ . 



========
Synopsis
========

::

    update-assume-role-policy
  --role-name <value>
  --policy-document <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--role-name`` (string)


  The name of the role to update.

  

``--policy-document`` (string)


  The policy that grants an entity permission to assume the role.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To update the trust policy for an IAM role**

The following ``update-assume-role-policy`` command updates the trust policy for the role named ``Test-Role``::

  aws iam update-assume-role-policy --role-name Test-Tole --policy-document file://Test-Role-Trust-Policy.json

The trust policy is defined as a JSON document in the *Test-Role-Trust-Policy.json* file. (The file name and extension
do not have significance.) The trust policy must specify a principal.

To update the permissions policy for a role, use the ``put-role-policy`` command.

For more information, see `Creating a Role`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html




======
Output
======

None

.. _Using Roles to Delegate Permissions and Federate Identities: http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-toplevel.html
