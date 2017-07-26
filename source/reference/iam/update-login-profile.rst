[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-login-profile:


********************
update-login-profile
********************



===========
Description
===========



Changes the password for the specified user.

 

Users can change their own passwords by calling  change-password . For more information about modifying passwords, see `Managing Passwords`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    update-login-profile
  --user-name <value>
  [--password <value>]
  [--password-reset-required | --no-password-reset-required]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user whose password you want to update.

  

``--password`` (string)


  The new password for the specified user.

  

``--password-reset-required`` | ``--no-password-reset-required`` (boolean)


  Require the specified user to set a new password on next sign-in.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To update the password for an IAM user**

The following ``update-login-profile`` command creates a new password for the IAM user named ``Bob``::

  aws iam update-login-profile --user-name Bob --password <password>

To set a password policy for the account, use the ``update-account-password-policy`` command. If the new password
violates the account password policy, the command returns a ``PasswordPolicyViolation`` error.

If the account password policy allows them to, IAM users can change their own passwords using the ``change-password`` command.

Store the password in a secure place. If the password is lost, it cannot be recovered, and you must create a new one using the ``create-login-profile`` command.

For more information, see `Managing Passwords`_ in the *Using IAM* guide.

.. _`Managing Passwords`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingLogins.html




======
Output
======

None

.. _Managing Passwords: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingLogins.html
