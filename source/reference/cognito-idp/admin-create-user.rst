[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp admin-create-user:


*****************
admin-create-user
*****************



===========
Description
===========



Creates a new user in the specified user pool and sends a welcome message via email or phone (SMS). This message is based on a template that you configured in your call to `create-user-pool <API_CreateUserPool.html>`_ or `update-user-pool <API_UpdateUserPool.html>`_ . This template includes your custom sign-up instructions and placeholders for user name and temporary password.

 

Requires developer credentials.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/AdminCreateUser>`_


========
Synopsis
========

::

    admin-create-user
  --user-pool-id <value>
  --username <value>
  [--user-attributes <value>]
  [--validation-data <value>]
  [--temporary-password <value>]
  [--force-alias-creation | --no-force-alias-creation]
  [--message-action <value>]
  [--desired-delivery-mediums <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool where the user will be created.

  

``--username`` (string)


  The username for the user. Must be unique within the user pool. Must be a UTF-8 string between 1 and 128 characters. After the user is created, the username cannot be changed.

  

``--user-attributes`` (list)


  An array of name-value pairs that contain user attributes and attribute values to be set for the user to be created. You can create a user without specifying any attributes other than ``Username`` . However, any attributes that you specify as required (in `create-user-pool <API_CreateUserPool.html>`_ or in the **Attributes** tab of the console) must be supplied either by you (in your call to ``admin-create-user`` ) or by the user (when he or she signs up in response to your welcome message).

   

  For custom attributes, you must prepend the ``custom:`` prefix to the attribute name.

   

  To send a message inviting the user to sign up, you must specify the user's email address or phone number. This can be done in your call to admin-create-user or in the **Users** tab of the Amazon Cognito console for managing your user pools.

   

  In your call to ``admin-create-user`` , you can set the ``email_verified`` attribute to ``True`` , and you can set the ``phone_number_verified`` attribute to ``True`` . (You can also do this by calling `admin-update-user-attributes <API_AdminUpdateUserAttributes.html>`_ .)

   

   
  * **email** : The email address of the user to whom the message that contains the code and username will be sent. Required if the ``email_verified`` attribute is set to ``True`` , or if ``"EMAIL"`` is specified in the ``DesiredDeliveryMediums`` parameter. 
   
  * **phone_number** : The phone number of the user to whom the message that contains the code and username will be sent. Required if the ``phone_number_verified`` attribute is set to ``True`` , or if ``"SMS"`` is specified in the ``DesiredDeliveryMediums`` parameter. 
   

  



Shorthand Syntax::

    Name=string,Value=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string"
    }
    ...
  ]



``--validation-data`` (list)


  The user's validation data. This is an array of name-value pairs that contain user attributes and attribute values that you can use for custom validation, such as restricting the types of user accounts that can be registered. For example, you might choose to allow or disallow user sign-up based on the user's domain.

   

  To configure custom validation, you must create a Pre Sign-up Lambda trigger for the user pool as described in the Amazon Cognito Developer Guide. The Lambda trigger receives the validation data and uses it in the validation process.

   

  The user's validation data is not persisted.

  



Shorthand Syntax::

    Name=string,Value=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string"
    }
    ...
  ]



``--temporary-password`` (string)


  The user's temporary password. This password must conform to the password policy that you specified when you created the user pool.

   

  The temporary password is valid only once. To complete the Admin Create User flow, the user must enter the temporary password in the sign-in page along with a new password to be used in all future sign-ins.

   

  This parameter is not required. If you do not specify a value, Amazon Cognito generates one for you.

   

  The temporary password can only be used until the user account expiration limit that you specified when you created the user pool. To reset the account after that time limit, you must call ``admin-create-user`` again, specifying ``"RESEND"`` for the ``MessageAction`` parameter.

  

``--force-alias-creation`` | ``--no-force-alias-creation`` (boolean)


  This parameter is only used if the ``phone_number_verified`` or ``email_verified`` attribute is set to ``True`` . Otherwise, it is ignored.

   

  If this parameter is set to ``True`` and the phone number or email address specified in the UserAttributes parameter already exists as an alias with a different user, the API call will migrate the alias from the previous user to the newly created user. The previous user will no longer be able to log in using that alias.

   

  If this parameter is set to ``False`` , the API throws an ``AliasExistsException`` error if the alias already exists. The default value is ``False`` .

  

``--message-action`` (string)


  Set to ``"RESEND"`` to resend the invitation message to a user that already exists and reset the expiration limit on the user's account. Set to ``"SUPPRESS"`` to suppress sending the message. Only one value can be specified.

  

  Possible values:

  
  *   ``RESEND``

  
  *   ``SUPPRESS``

  

  

``--desired-delivery-mediums`` (list)


  Specify ``"EMAIL"`` if email will be used to send the welcome message. Specify ``"SMS"`` if the phone number will be used. The default value is ``"SMS"`` . More than one value can be specified.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    SMS
    EMAIL





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

User -> (structure)

  

  The user returned in the request to create a new user.

  

  Username -> (string)

    

    The user name of the user you wish to describe.

    

    

  Attributes -> (list)

    

    A container with information about the user type attributes.

    

    (structure)

      

      Specifies whether the attribute is standard or custom.

      

      Name -> (string)

        

        The name of the attribute.

        

        

      Value -> (string)

        

        The value of the attribute.

        

        

      

    

  UserCreateDate -> (timestamp)

    

    The creation date of the user.

    

    

  UserLastModifiedDate -> (timestamp)

    

    The last modified date of the user.

    

    

  Enabled -> (boolean)

    

    Specifies whether the user is enabled.

    

    

  UserStatus -> (string)

    

    The user status. Can be one of the following:

     

     
    * UNCONFIRMED - User has been created but not confirmed. 
     
    * CONFIRMED - User has been confirmed. 
     
    * ARCHIVED - User is no longer active. 
     
    * COMPROMISED - User is disabled due to a potential security threat. 
     
    * UNKNOWN - User status is not known. 
     

    

    

  MFAOptions -> (list)

    

    The MFA options for the user.

    

    (structure)

      

      Specifies the different settings for multi-factor authentication (MFA).

      

      DeliveryMedium -> (string)

        

        The delivery medium (email message or SMS message) to send the MFA code.

        

        

      AttributeName -> (string)

        

        The attribute name of the MFA option type.

        

        

      

    

  

