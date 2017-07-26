[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-account-password-policy:


******************************
update-account-password-policy
******************************



===========
Description
===========



Updates the password policy settings for the AWS account.

 

.. note::

   

  This action does not support partial updates. No parameters are required, but if you do not specify a parameter, that parameter's value reverts to its default value. See the **Request Parameters** section for each parameter's default value.

   

 

For more information about using a password policy, see `Managing an IAM Password Policy <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingPasswordPolicies.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UpdateAccountPasswordPolicy>`_


========
Synopsis
========

::

    update-account-password-policy
  [--minimum-password-length <value>]
  [--require-symbols | --no-require-symbols]
  [--require-numbers | --no-require-numbers]
  [--require-uppercase-characters | --no-require-uppercase-characters]
  [--require-lowercase-characters | --no-require-lowercase-characters]
  [--allow-users-to-change-password | --no-allow-users-to-change-password]
  [--max-password-age <value>]
  [--password-reuse-prevention <value>]
  [--hard-expiry | --no-hard-expiry]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--minimum-password-length`` (integer)


  The minimum number of characters allowed in an IAM user password.

   

  Default value: 6

  

``--require-symbols`` | ``--no-require-symbols`` (boolean)


  Specifies whether IAM user passwords must contain at least one of the following non-alphanumeric characters:

   

  ! @ # $ % ^ amp; * ( ) _ + - = [ ] { } | '

   

  Default value: false

  

``--require-numbers`` | ``--no-require-numbers`` (boolean)


  Specifies whether IAM user passwords must contain at least one numeric character (0 to 9).

   

  Default value: false

  

``--require-uppercase-characters`` | ``--no-require-uppercase-characters`` (boolean)


  Specifies whether IAM user passwords must contain at least one uppercase character from the ISO basic Latin alphabet (A to Z).

   

  Default value: false

  

``--require-lowercase-characters`` | ``--no-require-lowercase-characters`` (boolean)


  Specifies whether IAM user passwords must contain at least one lowercase character from the ISO basic Latin alphabet (a to z).

   

  Default value: false

  

``--allow-users-to-change-password`` | ``--no-allow-users-to-change-password`` (boolean)


  Allows all IAM users in your account to use the AWS Management Console to change their own passwords. For more information, see `Letting IAM Users Change Their Own Passwords <http://docs.aws.amazon.com/IAM/latest/UserGuide/HowToPwdIAMUser.html>`_ in the *IAM User Guide* .

   

  Default value: false

  

``--max-password-age`` (integer)


  The number of days that an IAM user password is valid. The default value of 0 means IAM user passwords never expire.

   

  Default value: 0

  

``--password-reuse-prevention`` (integer)


  Specifies the number of previous passwords that IAM users are prevented from reusing. The default value of 0 means IAM users are not prevented from reusing previous passwords.

   

  Default value: 0

  

``--hard-expiry`` | ``--no-hard-expiry`` (boolean)


  Prevents IAM users from setting a new password after their password has expired.

   

  Default value: false

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To set or change the current account password policy**

The following ``update-account-password-policy`` command sets the password policy to require a minimum length of eight
characters and to require one or more numbers in the password::

    aws iam update-account-password-policy --minimum-password-length 8 --require-numbers

Changes to an account's password policy affect any new passwords that are created for IAM users in the account. Password
policy changes do not affect existing passwords.

For more information, see `Setting an Account Password Policy for IAM Users`_ in the *Using IAM* guide.

.. _`Setting an Account Password Policy for IAM Users`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingPasswordPolicies.html



======
Output
======

None