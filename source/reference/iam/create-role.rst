[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-role:


***********
create-role
***********



===========
Description
===========



Creates a new role for your AWS account. For more information about roles, go to `Working with Roles <http://docs.aws.amazon.com/IAM/latest/UserGuide/WorkingWithRoles.html>`_ . For information about limitations on role names and the number of roles you can create, go to `Limitations on IAM Entities <http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/CreateRole>`_


========
Synopsis
========

::

    create-role
  [--path <value>]
  --role-name <value>
  --assume-role-policy-document <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--path`` (string)


  The path to the role. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *IAM User Guide* .

   

  This parameter is optional. If it is not included, it defaults to a slash (/).

   

  This paramater allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

  

``--role-name`` (string)


  The name of the role to create.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: _+=,.@-

   

  Role names are not distinguished by case. For example, you cannot create roles named both "PRODROLE" and "prodrole".

  

``--assume-role-policy-document`` (string)


  The trust relationship policy document that grants an entity permission to assume the role.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ used to validate this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range as well as the printable characters in the Basic Latin and Latin-1 Supplement character set (through \u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

  

``--description`` (string)


  A customer-provided description of the role.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an IAM role**

The following ``create-role`` command creates a role named ``Test-Role`` and attaches a trust policy to it::

  aws iam create-role --role-name Test-Role --assume-role-policy-document file://Test-Role-Trust-Policy.json

Output::

  {
    "Role": {
        "AssumeRolePolicyDocument": "<URL-encoded-JSON>",
        "RoleId": "AKIAIOSFODNN7EXAMPLE",
        "CreateDate": "2013-06-07T20:43:32.821Z",
        "RoleName": "Test-Role",
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:role/Test-Role"
    }
  }

The trust policy is defined as a JSON document in the *Test-Role-Trust-Policy.json* file. (The file name and extension do not have significance.) The trust policy must specify a principal.

To attach a permissions policy to a role, use the ``put-role-policy`` command.

For more information, see `Creating a Role`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html



======
Output
======

Role -> (structure)

  

  A structure containing details about the new role.

  

  Path -> (string)

    

    The path to the role. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

    

    

  RoleName -> (string)

    

    The friendly name that identifies the role.

    

    

  RoleId -> (string)

    

    The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *IAM User Guide* guide. 

    

    

  CreateDate -> (timestamp)

    

    The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the role was created.

    

    

  AssumeRolePolicyDocument -> (string)

    

    The policy that grants an entity permission to assume the role.

    

    

  Description -> (string)

    

    A description of the role that you provide.

    

    

  

