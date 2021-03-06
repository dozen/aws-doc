[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-login-profile:


********************
update-login-profile
********************



===========
Description
===========



Changes the password for the specified IAM user.

 

IAM users can change their own passwords by calling  change-password . For more information about modifying passwords, see `Managing Passwords <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingLogins.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UpdateLoginProfile>`_


========
Synopsis
========

::

    update-login-profile
  --user-name <value>
  [--password <value>]
  [--password-reset-required | --no-password-reset-required]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the user whose password you want to update.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--password`` (string)


  The new password for the specified IAM user.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ used to validate this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range as well as the printable characters in the Basic Latin and Latin-1 Supplement character set (through \u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D). However, the format can be further restricted by the account administrator by setting a password policy on the AWS account. For more information, see  update-account-password-policy .

  

``--password-reset-required`` | ``--no-password-reset-required`` (boolean)


  Allows this new password to be used only once by requiring the specified IAM user to set a new password on next sign-in.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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