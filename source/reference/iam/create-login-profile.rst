[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-login-profile:


********************
create-login-profile
********************



===========
Description
===========



Creates a password for the specified user, giving the user the ability to access AWS services through the AWS Management Console. For more information about managing passwords, see `Managing Passwords`_ in the *Using IAM* guide. 



========
Synopsis
========

::

    create-login-profile
  --user-name <value>
  --password <value>
  [--password-reset-required | --no-password-reset-required]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user to create a password for.

  

``--password`` (string)


  The new password for the user.

  

``--password-reset-required`` | ``--no-password-reset-required`` (boolean)


  Specifies whether the user is required to set a new password on next sign-in. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a password for an IAM user**

To create a password for an IAM user, we recommend using the ``--cli-input-json`` parameter to pass a JSON file that contains the password. Using this method, you can create a strong password with non-alphanumeric characters. It can be difficult to create a password with non-alphanumeric characters when you pass it as a command line parameter.

To use the ``--cli-input-json`` parameter, start by using the ``create-login-profile`` command with the ``--generate-cli-skeleton`` parameter, as in the following example::

  aws iam create-login-profile --generate-cli-skeleton > create-login-profile.json

The previous command creates a JSON file called create-login-profile.json that you can use to fill in the information for a subsequent ``create-login-profile`` command. For example::

  {
      "UserName": "Bob",
      "Password": "&1-3a6u:RA0djs",
      "PasswordResetRequired": true
  }

Next, to create a password for an IAM user, use the ``create-login-profile`` command again, this time passing the ``--cli-input-json`` parameter to specify your JSON file. The following ``create-login-profile`` command uses the ``--cli-input-json`` parameter with a JSON file called create-login-profile.json::

  aws iam create-login-profile --cli-input-json file://create-login-profile.json

Output::

  {
      "LoginProfile": {
          "UserName": "Bob",
          "CreateDate": "2015-03-10T20:55:40.274Z",
          "PasswordResetRequired": true
      }
  }

If the new password violates the account password policy, the command returns a ``PasswordPolicyViolation`` error.

To change the password for a user that already has one, use ``update-login-profile``. To set a password policy for the account, use the ``update-account-password-policy`` command. 

If the account password policy allows them to, IAM users can change their own passwords using the ``change-password`` command.

For more information, see `Managing Passwords for IAM Users`_ in the *Using IAM* guide.

.. _`Managing Passwords for IAM Users`: http://docs.aws.amazon.com/IAM/latest/UserGuide/credentials-add-pwd-for-user.html

======
Output
======

LoginProfile -> (structure)

  

  The user name and password create date.

  

  UserName -> (string)

    

    The name of the user, which can be used for signing in to the AWS Management Console.

    

    

  CreateDate -> (timestamp)

    

    The date when the password for the user was created.

    

    

  PasswordResetRequired -> (boolean)

    

    Specifies whether the user is required to set a new password on next sign-in.

    

    

  



.. _Managing Passwords: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingLogins.html
