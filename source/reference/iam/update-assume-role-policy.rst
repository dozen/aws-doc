[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-assume-role-policy:


*************************
update-assume-role-policy
*************************



===========
Description
===========



Updates the policy that grants an IAM entity permission to assume a role. This is typically referred to as the "role trust policy". For more information about roles, go to `Using Roles to Delegate Permissions and Federate Identities <http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-toplevel.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UpdateAssumeRolePolicy>`_


========
Synopsis
========

::

    update-assume-role-policy
  --role-name <value>
  --policy-document <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-name`` (string)


  The name of the role to update with the new policy.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: _+=,.@-

  

``--policy-document`` (string)


  The policy that grants an entity permission to assume the role.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ used to validate this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range as well as the printable characters in the Basic Latin and Latin-1 Supplement character set (through \u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update the trust policy for an IAM role**

The following ``update-assume-role-policy`` command updates the trust policy for the role named ``Test-Role``::

  aws iam update-assume-role-policy --role-name Test-Role --policy-document file://Test-Role-Trust-Policy.json

The trust policy is defined as a JSON document in the *Test-Role-Trust-Policy.json* file. (The file name and extension
do not have significance.) The trust policy must specify a principal.

To update the permissions policy for a role, use the ``put-role-policy`` command.

For more information, see `Creating a Role`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html




======
Output
======

None