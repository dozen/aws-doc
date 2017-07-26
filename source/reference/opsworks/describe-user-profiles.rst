[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-user-profiles:


**********************
describe-user-profiles
**********************



===========
Description
===========



Describe specified users.

 

**Required Permissions** : To use this action, an IAM user must have an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-user-profiles
  [--iam-user-arns <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--iam-user-arns`` (list)


  An array of IAM user ARNs that identify the users to be described. 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe user profiles**

The following ``describe-user-profiles`` command describes the account's user profiles. ::

  aws opsworks --region us-east-1 describe-user-profiles

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*::

  {
    "UserProfiles": [
      {
        "IamUserArn": "arn:aws:iam::123456789012:user/someuser",
        "SshPublicKey": "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEAkOuP7i80q3Cko...",
        "AllowSelfManagement": true,
        "Name": "someuser",
        "SshUsername": "someuser"
      },
      {
        "IamUserArn": "arn:aws:iam::123456789012:user/cli-user-test",
        "AllowSelfManagement": true,
        "Name": "cli-user-test",
        "SshUsername": "myusername"
      }
    ]
  }

**More Information**

For more information, see `Managing AWS OpsWorks Users`_ in the *AWS OpsWorks User Guide*.

.. _`Managing AWS OpsWorks Users`: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users-manage.html



======
Output
======

UserProfiles -> (list)

  

  A ``Users`` object that describes the specified users.

  

  (structure)

    

    Describes a user's SSH information.

    

    IamUserArn -> (string)

      

      The user's IAM ARN.

      

      

    Name -> (string)

      

      The user's name.

      

      

    SshUsername -> (string)

      

      The user's SSH user name.

      

      

    SshPublicKey -> (string)

      

      The user's SSH public key.

      

      

    AllowSelfManagement -> (boolean)

      

      Whether users can specify their own SSH public key through the My Settings page. For more information, see `Managing User Permissions`_ .

      

      

    

  



.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/security-settingsshkey.html
