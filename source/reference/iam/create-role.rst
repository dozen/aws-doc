[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-role:


***********
create-role
***********



===========
Description
===========



Creates a new role for your AWS account. For more information about roles, go to `Working with Roles`_ . For information about limitations on role names and the number of roles you can create, go to `Limitations on IAM Entities`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    create-role
  [--path <value>]
  --role-name <value>
  --assume-role-policy-document <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--path`` (string)


  The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

   

  This parameter is optional. If it is not included, it defaults to a slash (/).

  

``--role-name`` (string)


  The name of the role to create.

  

``--assume-role-policy-document`` (string)


  The trust relationship policy document that grants an entity permission to assume the role.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  Information about the role.

  

  Path -> (string)

    

    The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

    

    

  RoleName -> (string)

    

    The friendly name that identifies the role.

    

    

  RoleId -> (string)

    

    The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

    

    

  CreateDate -> (timestamp)

    

    The date and time, in `ISO 8601 date-time format`_ , when the role was created.

    

    

  AssumeRolePolicyDocument -> (string)

    

    The policy that grants an entity permission to assume the role.

    

    

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Working with Roles: http://docs.aws.amazon.com/IAM/latest/UserGuide/WorkingWithRoles.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Limitations on IAM Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html
