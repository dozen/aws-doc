[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam put-role-policy:


***************
put-role-policy
***************



===========
Description
===========



Adds or updates an inline policy document that is embedded in the specified IAM role.

 

When you embed an inline policy in a role, the inline policy is used as part of the role's access (permissions) policy. The role's trust policy is created at the same time as the role, using  create-role . You can update a role's trust policy using  update-assume-role-policy . For more information about IAM roles, go to `Using Roles to Delegate Permissions and Federate Identities <http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-toplevel.html>`_ .

 

A role can also have a managed policy attached to it. To attach a managed policy to a role, use  attach-role-policy . To create a new managed policy, use  create-policy . For information about policies, see `Managed Policies and Inline Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html>`_ in the *IAM User Guide* .

 

For information about limits on the number of inline policies that you can embed with a role, see `Limitations on IAM Entities <http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html>`_ in the *IAM User Guide* .

 

.. note::

   

  Because policy documents can be large, you should use POST rather than GET when calling ``put-role-policy`` . For general information about using the Query API with IAM, go to `Making Query Requests <http://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_UsingQueryAPI.html>`_ in the *IAM User Guide* .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/PutRolePolicy>`_


========
Synopsis
========

::

    put-role-policy
  --role-name <value>
  --policy-name <value>
  --policy-document <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-name`` (string)


  The name of the role to associate the policy with.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: _+=,.@-

  

``--policy-name`` (string)


  The name of the policy document.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--policy-document`` (string)


  The policy document.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ used to validate this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range as well as the printable characters in the Basic Latin and Latin-1 Supplement character set (through \u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attach a permissions policy to an IAM role**

The following ``put-role-policy`` command adds a permissions policy to the role named ``Test-Role``::

  aws iam put-role-policy --role-name Test-Role --policy-name ExamplePolicy --policy-document file://AdminPolicy.json

The policy is defined as a JSON document in the *AdminPolicy.json* file. (The file name and extension do not have significance.)

To attach a trust policy to a role, use the ``update-assume-role-policy`` command.

For more information, see `Creating a Role`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html



======
Output
======

None