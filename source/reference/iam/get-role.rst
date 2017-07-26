[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-role:


********
get-role
********



===========
Description
===========



Retrieves information about the specified role, including the role's path, GUID, ARN, and the policy granting permission to assume the role. For more information about ARNs, go to `ARNs`_ . For more information about roles, go to `Working with Roles`_ . 



========
Synopsis
========

::

    get-role
  --role-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--role-name`` (string)


  The name of the role to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about an IAM role**

The following ``get-role`` command gets information about the role named ``Test-Role``::

  aws iam get-role --role-name Test-Role

Output::

  {
    "Role": {
        "AssumeRolePolicyDocument": "<URL-encoded-JSON>",
        "RoleId": "AIDIODR4TAW7CSEXAMPLE",
        "CreateDate": "2013-04-18T05:01:58Z",
        "RoleName": "Test-Role",
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:role/Test-Role"
    }
  }

The command displays the trust policy attached to the role. To list the permissions policies attached to a role, use the ``list-role-policies`` command.

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

    

    

  



.. _ARNs: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html#Identifiers_ARNs
.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Working with Roles: http://docs.aws.amazon.com/IAM/latest/UserGuide/WorkingWithRoles.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
