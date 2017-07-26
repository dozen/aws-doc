[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-account-password-policy:


***************************
get-account-password-policy
***************************



===========
Description
===========



Retrieves the password policy for the AWS account. For more information about using a password policy, go to `Managing an IAM Password Policy`_ . 



========
Synopsis
========

::

    get-account-password-policy
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  Contains information about the account password policy.

   

  This data type is used as a response element in the  get-account-password-policy action. 

  

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

    

    

  



.. _Managing an IAM Password Policy: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingPasswordPolicies.html
