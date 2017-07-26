[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam change-password:


***************
change-password
***************



===========
Description
===========



Changes the password of the IAM user who is calling this action. The root account password is not affected by this action. 

 

To change the password for a different user, see  update-login-profile . For more information about modifying passwords, see `Managing Passwords`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    change-password
  --old-password <value>
  --new-password <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--old-password`` (string)


  The IAM user's current password.

  

``--new-password`` (string)


  The new password. The new password must conform to the AWS account's password policy, if one exists.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To change the password for your IAM user**

To change the password for your IAM user, we recommend using the ``--cli-input-json`` parameter to pass a JSON file that contains your old and new passwords. Using this method, you can use strong passwords with non-alphanumeric characters. It can be difficult to use passwords with non-alphanumeric characters when you pass them as command line parameters. To use the ``--cli-input-json`` parameter, start by using the ``change-password`` command with the ``--generate-cli-skeleton`` parameter, as in the following example::

  aws iam change-password --generate-cli-skeleton > change-password.json

The previous command creates a JSON file called change-password.json that you can use to fill in your old and new passwords. For example, the file might look like this::

  {
      "OldPassword": "3s0K_;xh4~8XXI",
      "NewPassword": "]35d/{pB9Fo9wJ"
  }

Next, to change your password, use the ``change-password`` command again, this time passing the ``--cli-input-json`` parameter to specify your JSON file. The following ``change-password`` command uses the ``--cli-input-json`` parameter with a JSON file called change-password.json::

  aws iam change-password --cli-input-json file://change-password.json

This command can be called by IAM users only. If this command is called using AWS account (root) credentials, the command returns an ``InvalidUserType`` error.

For more information, see `How IAM Users Change Their Own Password`_ in the *Using IAM* guide.

.. _`How IAM Users Change Their Own Password`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingUserPwdSelf.html

======
Output
======

None

.. _Managing Passwords: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingLogins.html
