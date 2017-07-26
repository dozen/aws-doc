[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-account-password-policy:


***************************
get-account-password-policy
***************************



===========
Description
===========



Retrieves the password policy for the AWS account. For more information about using a password policy, go to `Managing an IAM Password Policy <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingPasswordPolicies.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetAccountPasswordPolicy>`_


========
Synopsis
========

::

    get-account-password-policy
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To see the current account password policy**

The following ``get-account-password-policy`` command displays details about the password policy for the current account::

    aws iam get-account-password-policy

Output::

  {
      "PasswordPolicy": {
          "AllowUsersToChangePassword": false,
          "RequireLowercaseCharacters": false,
          "RequireUppercaseCharacters": false,
          "MinimumPasswordLength": 8,
          "RequireNumbers": true,
          "RequireSymbols": true
      }
  }

If no password policy is defined for the account, the command returns a ``NoSuchEntity`` error.

For more information, see `Managing an IAM Password Policy`_ in the *Using IAM* guide.

.. _`Managing an IAM Password Policy`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingPasswordPolicies.html


======
Output
======

PasswordPolicy -> (structure)

  

  A structure that contains details about the account's password policy.

  

  MinimumPasswordLength -> (integer)

    

    Minimum length to require for IAM user passwords.

    

    

  RequireSymbols -> (boolean)

    

    Specifies whether to require symbols for IAM user passwords.

    

    

  RequireNumbers -> (boolean)

    

    Specifies whether to require numbers for IAM user passwords.

    

    

  RequireUppercaseCharacters -> (boolean)

    

    Specifies whether to require uppercase characters for IAM user passwords.

    

    

  RequireLowercaseCharacters -> (boolean)

    

    Specifies whether to require lowercase characters for IAM user passwords.

    

    

  AllowUsersToChangePassword -> (boolean)

    

    Specifies whether IAM users are allowed to change their own password.

    

    

  ExpirePasswords -> (boolean)

    

    Indicates whether passwords in the account expire. Returns true if MaxPasswordAge is contains a value greater than 0. Returns false if MaxPasswordAge is 0 or not present.

    

    

  MaxPasswordAge -> (integer)

    

    The number of days that an IAM user password is valid.

    

    

  PasswordReusePrevention -> (integer)

    

    Specifies the number of previous passwords that IAM users are prevented from reusing.

    

    

  HardExpiry -> (boolean)

    

    Specifies whether IAM users are prevented from setting a new password after their password has expired.

    

    

  

