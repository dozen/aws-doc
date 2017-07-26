[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp create-user-pool:


****************
create-user-pool
****************



===========
Description
===========



Creates a new Amazon Cognito user pool and sets the password policy for the pool.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/CreateUserPool>`_


========
Synopsis
========

::

    create-user-pool
  --pool-name <value>
  [--policies <value>]
  [--lambda-config <value>]
  [--auto-verified-attributes <value>]
  [--alias-attributes <value>]
  [--username-attributes <value>]
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
  [--schema <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pool-name`` (string)


  A string used to name the user pool.

  

``--policies`` (structure)


  The policies associated with the new user pool.

  



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


  The Lambda trigger configuration information for the new user pool.

  



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


  The attributes to be auto-verified. Possible values: **email** , **phone_number** .

  



Syntax::

  "string" "string" ...

  Where valid values are:
    phone_number
    email





``--alias-attributes`` (list)


  Attributes supported as an alias for this user pool. Possible values: **phone_number** , **email** , or **preferred_username** .

  



Syntax::

  "string" "string" ...

  Where valid values are:
    phone_number
    email
    preferred_username





``--username-attributes`` (list)


  Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    phone_number
    email





``--sms-verification-message`` (string)


  A string representing the SMS verification message.

  

``--email-verification-message`` (string)


  A string representing the email verification message.

  

``--email-verification-subject`` (string)


  A string representing the email verification subject.

  

``--sms-authentication-message`` (string)


  A string representing the SMS authentication message.

  

``--mfa-configuration`` (string)


  Specifies MFA configuration details.

  

  Possible values:

  
  *   ``OFF``

  
  *   ``ON``

  
  *   ``OPTIONAL``

  

  

``--device-configuration`` (structure)


  The device configuration.

  



Shorthand Syntax::

    ChallengeRequiredOnNewDevice=boolean,DeviceOnlyRememberedOnUserPrompt=boolean




JSON Syntax::

  {
    "ChallengeRequiredOnNewDevice": true|false,
    "DeviceOnlyRememberedOnUserPrompt": true|false
  }



``--email-configuration`` (structure)


  The email configuration.

  



Shorthand Syntax::

    SourceArn=string,ReplyToEmailAddress=string




JSON Syntax::

  {
    "SourceArn": "string",
    "ReplyToEmailAddress": "string"
  }



``--sms-configuration`` (structure)


  The SMS configuration.

  



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



``--schema`` (list)


  An array of schema attributes for the new user pool. These attributes can be standard or custom attributes.

  



Shorthand Syntax::

    Name=string,AttributeDataType=string,DeveloperOnlyAttribute=boolean,Mutable=boolean,Required=boolean,NumberAttributeConstraints={MinValue=string,MaxValue=string},StringAttributeConstraints={MinLength=string,MaxLength=string} ...




JSON Syntax::

  [
    {
      "Name": "string",
      "AttributeDataType": "String"|"Number"|"DateTime"|"Boolean",
      "DeveloperOnlyAttribute": true|false,
      "Mutable": true|false,
      "Required": true|false,
      "NumberAttributeConstraints": {
        "MinValue": "string",
        "MaxValue": "string"
      },
      "StringAttributeConstraints": {
        "MinLength": "string",
        "MaxLength": "string"
      }
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

UserPool -> (structure)

  

  A container for the user pool details.

  

  Id -> (string)

    

    The ID of the user pool.

    

    

  Name -> (string)

    

    The name of the user pool.

    

    

  Policies -> (structure)

    

    A container for the policies associated with a user pool.

    

    PasswordPolicy -> (structure)

      

      A container for information about the user pool password policy.

      

      MinimumLength -> (integer)

        

        The minimum length of the password policy that you have set. Cannot be less than 6.

        

        

      RequireUppercase -> (boolean)

        

        In the password policy that you have set, refers to whether you have required users to use at least one uppercase letter in their password.

        

        

      RequireLowercase -> (boolean)

        

        In the password policy that you have set, refers to whether you have required users to use at least one lowercase letter in their password.

        

        

      RequireNumbers -> (boolean)

        

        In the password policy that you have set, refers to whether you have required users to use at least one number in their password.

        

        

      RequireSymbols -> (boolean)

        

        In the password policy that you have set, refers to whether you have required users to use at least one symbol in their password.

        

        

      

    

  LambdaConfig -> (structure)

    

    A container for the AWS Lambda triggers associated with a user pool.

    

    PreSignUp -> (string)

      

      A pre-registration AWS Lambda trigger.

      

      

    CustomMessage -> (string)

      

      A custom Message AWS Lambda trigger.

      

      

    PostConfirmation -> (string)

      

      A post-confirmation AWS Lambda trigger.

      

      

    PreAuthentication -> (string)

      

      A pre-authentication AWS Lambda trigger.

      

      

    PostAuthentication -> (string)

      

      A post-authentication AWS Lambda trigger.

      

      

    DefineAuthChallenge -> (string)

      

      Defines the authentication challenge.

      

      

    CreateAuthChallenge -> (string)

      

      Creates an authentication challenge.

      

      

    VerifyAuthChallengeResponse -> (string)

      

      Verifies the authentication challenge response.

      

      

    

  Status -> (string)

    

    The status of a user pool.

    

    

  LastModifiedDate -> (timestamp)

    

    The date the user pool was last modified.

    

    

  CreationDate -> (timestamp)

    

    The date the user pool was created.

    

    

  SchemaAttributes -> (list)

    

    A container with the schema attributes of a user pool.

    

    (structure)

      

      Contains information about the schema attribute.

      

      Name -> (string)

        

        A schema attribute of the name type.

        

        

      AttributeDataType -> (string)

        

        The attribute data type.

        

        

      DeveloperOnlyAttribute -> (boolean)

        

        Specifies whether the attribute type is developer only.

        

        

      Mutable -> (boolean)

        

        Specifies whether the attribute can be changed once it has been created.

        

        

      Required -> (boolean)

        

        Specifies whether a user pool attribute is required. If the attribute is required and the user does not provide a value, registration or sign-in will fail.

        

        

      NumberAttributeConstraints -> (structure)

        

        Specifies the constraints for an attribute of the number type.

        

        MinValue -> (string)

          

          The minimum value of an attribute that is of the number data type.

          

          

        MaxValue -> (string)

          

          The maximum value of an attribute that is of the number data type.

          

          

        

      StringAttributeConstraints -> (structure)

        

        Specifies the constraints for an attribute of the string type.

        

        MinLength -> (string)

          

          The minimum length of an attribute value of the string type.

          

          

        MaxLength -> (string)

          

          The maximum length of an attribute value of the string type.

          

          

        

      

    

  AutoVerifiedAttributes -> (list)

    

    Specifies the attributes that are auto-verified in a user pool.

    

    (string)

      

      

    

  AliasAttributes -> (list)

    

    Specifies the attributes that are aliased in a user pool.

    

    (string)

      

      

    

  UsernameAttributes -> (list)

    

    Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up.

    

    (string)

      

      

    

  SmsVerificationMessage -> (string)

    

    The contents of the SMS verification message.

    

    

  EmailVerificationMessage -> (string)

    

    The contents of the email verification message.

    

    

  EmailVerificationSubject -> (string)

    

    The subject of the email verification message.

    

    

  SmsAuthenticationMessage -> (string)

    

    The contents of the SMS authentication message.

    

    

  MfaConfiguration -> (string)

    

    Can be one of the following values:

     

     
    * ``OFF`` - MFA tokens are not required and cannot be specified during user registration. 
     
    * ``ON`` - MFA tokens are required for all user registrations. You can only specify required when you are initially creating a user pool. 
     
    * ``OPTIONAL`` - Users have the option when registering to create an MFA token. 
     

    

    

  DeviceConfiguration -> (structure)

    

    The device configuration.

    

    ChallengeRequiredOnNewDevice -> (boolean)

      

      Indicates whether a challenge is required on a new device. Only applicable to a new device.

      

      

    DeviceOnlyRememberedOnUserPrompt -> (boolean)

      

      If true, a device is only remembered on user prompt.

      

      

    

  EstimatedNumberOfUsers -> (integer)

    

    A number estimating the size of the user pool.

    

    

  EmailConfiguration -> (structure)

    

    The email configuration.

    

    SourceArn -> (string)

      

      The Amazon Resource Name (ARN) of the email source.

      

      

    ReplyToEmailAddress -> (string)

      

      The REPLY-TO email address.

      

      

    

  SmsConfiguration -> (structure)

    

    The SMS configuration.

    

    SnsCallerArn -> (string)

      

      The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) caller.

      

      

    ExternalId -> (string)

      

      The external ID.

      

      

    

  UserPoolTags -> (map)

    

    The cost allocation tags for the user pool. For more information, see `Adding Cost Allocation Tags to Your User Pool <http://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-cost-allocation-tagging.html>`_  

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  SmsConfigurationFailure -> (string)

    

    The reason why the SMS configuration cannot send the messages to your users.

    

    

  EmailConfigurationFailure -> (string)

    

    The reason why the email configuration cannot send the messages to your users.

    

    

  AdminCreateUserConfig -> (structure)

    

    The configuration for ``admin-create-user`` requests.

    

    AllowAdminCreateUserOnly -> (boolean)

      

      Set to ``True`` if only the administrator is allowed to create user profiles. Set to ``False`` if users can sign themselves up via an app.

      

      

    UnusedAccountValidityDays -> (integer)

      

      The user account expiration limit, in days, after which the account is no longer usable. To reset the account after that time limit, you must call ``admin-create-user`` again, specifying ``"RESEND"`` for the ``MessageAction`` parameter. The default value for this parameter is 7.

      

      

    InviteMessageTemplate -> (structure)

      

      The message template to be used for the welcome message to new users.

      

      SMSMessage -> (string)

        

        The message template for SMS messages.

        

        

      EmailMessage -> (string)

        

        The message template for email messages.

        

        

      EmailSubject -> (string)

        

        The subject line for email messages.

        

        

      

    

  

