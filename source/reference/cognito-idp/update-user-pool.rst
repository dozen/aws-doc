[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp update-user-pool:


****************
update-user-pool
****************



===========
Description
===========



Updates the specified user pool with the specified attributes.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/UpdateUserPool>`_


========
Synopsis
========

::

    update-user-pool
  --user-pool-id <value>
  [--policies <value>]
  [--lambda-config <value>]
  [--auto-verified-attributes <value>]
  [--sms-verification-message <value>]
  [--email-verification-message <value>]
  [--email-verification-subject <value>]
  [--sms-authentication-message <value>]
  [--mfa-configuration <value>]
  [--device-configuration <value>]
  [--email-configuration <value>]
  [--sms-configuration <value>]
  [--user-pool-tags <value>]
  [--admin-create-user-config <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool you want to update.

  

``--policies`` (structure)


  A container with the policies you wish to update in a user pool.

  



Shorthand Syntax::

    PasswordPolicy={MinimumLength=integer,RequireUppercase=boolean,RequireLowercase=boolean,RequireNumbers=boolean,RequireSymbols=boolean}




JSON Syntax::

  {
    "PasswordPolicy": {
      "MinimumLength": integer,
      "RequireUppercase": true|false,
      "RequireLowercase": true|false,
      "RequireNumbers": true|false,
      "RequireSymbols": true|false
    }
  }



``--lambda-config`` (structure)


  The AWS Lambda configuration information from the request to update the user pool.

  



Shorthand Syntax::

    PreSignUp=string,CustomMessage=string,PostConfirmation=string,PreAuthentication=string,PostAuthentication=string,DefineAuthChallenge=string,CreateAuthChallenge=string,VerifyAuthChallengeResponse=string




JSON Syntax::

  {
    "PreSignUp": "string",
    "CustomMessage": "string",
    "PostConfirmation": "string",
    "PreAuthentication": "string",
    "PostAuthentication": "string",
    "DefineAuthChallenge": "string",
    "CreateAuthChallenge": "string",
    "VerifyAuthChallengeResponse": "string"
  }



``--auto-verified-attributes`` (list)


  The attributes that are automatically verified when the Amazon Cognito service makes a request to update user pools.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    phone_number
    email





``--sms-verification-message`` (string)


  A container with information about the SMS verification message.

  

``--email-verification-message`` (string)


  The contents of the email verification message.

  

``--email-verification-subject`` (string)


  The subject of the email verification message.

  

``--sms-authentication-message`` (string)


  The contents of the SMS authentication message.

  

``--mfa-configuration`` (string)


  Can be one of the following values:

   

   
  * ``OFF`` - MFA tokens are not required and cannot be specified during user registration. 
   
  * ``ON`` - MFA tokens are required for all user registrations. You can only specify required when you are initially creating a user pool. 
   
  * ``OPTIONAL`` - Users have the option when registering to create an MFA token. 
   

  

  Possible values:

  
  *   ``OFF``

  
  *   ``ON``

  
  *   ``OPTIONAL``

  

  

``--device-configuration`` (structure)


  Device configuration.

  



Shorthand Syntax::

    ChallengeRequiredOnNewDevice=boolean,DeviceOnlyRememberedOnUserPrompt=boolean




JSON Syntax::

  {
    "ChallengeRequiredOnNewDevice": true|false,
    "DeviceOnlyRememberedOnUserPrompt": true|false
  }



``--email-configuration`` (structure)


  Email configuration.

  



Shorthand Syntax::

    SourceArn=string,ReplyToEmailAddress=string




JSON Syntax::

  {
    "SourceArn": "string",
    "ReplyToEmailAddress": "string"
  }



``--sms-configuration`` (structure)


  SMS configuration.

  



Shorthand Syntax::

    SnsCallerArn=string,ExternalId=string




JSON Syntax::

  {
    "SnsCallerArn": "string",
    "ExternalId": "string"
  }



``--user-pool-tags`` (map)


  The cost allocation tags for the user pool. For more information, see `Adding Cost Allocation Tags to Your User Pool <http://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-cost-allocation-tagging.html>`_  

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--admin-create-user-config`` (structure)


  The configuration for ``admin-create-user`` requests.

  



Shorthand Syntax::

    AllowAdminCreateUserOnly=boolean,UnusedAccountValidityDays=integer,InviteMessageTemplate={SMSMessage=string,EmailMessage=string,EmailSubject=string}




JSON Syntax::

  {
    "AllowAdminCreateUserOnly": true|false,
    "UnusedAccountValidityDays": integer,
    "InviteMessageTemplate": {
      "SMSMessage": "string",
      "EmailMessage": "string",
      "EmailSubject": "string"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

