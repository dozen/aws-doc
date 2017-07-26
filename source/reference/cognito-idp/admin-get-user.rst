[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp admin-get-user:


**************
admin-get-user
**************



===========
Description
===========



Gets the specified user by user name in a user pool as an administrator. Works on any user.

 

Requires developer credentials.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/AdminGetUser>`_


========
Synopsis
========

::

    admin-get-user
  --user-pool-id <value>
  --username <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool where you want to get information about the user.

  

``--username`` (string)


  The user name of the user you wish to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Username -> (string)

  

  The user name of the user about whom you are receiving information.

  

  

UserAttributes -> (list)

  

  An array of name-value pairs representing user attributes.

  

  (structure)

    

    Specifies whether the attribute is standard or custom.

    

    Name -> (string)

      

      The name of the attribute.

      

      

    Value -> (string)

      

      The value of the attribute.

      

      

    

  

UserCreateDate -> (timestamp)

  

  The date the user was created.

  

  

UserLastModifiedDate -> (timestamp)

  

  The date the user was last modified.

  

  

Enabled -> (boolean)

  

  Indicates that the status is enabled.

  

  

UserStatus -> (string)

  

  The user status. Can be one of the following:

   

   
  * UNCONFIRMED - User has been created but not confirmed. 
   
  * CONFIRMED - User has been confirmed. 
   
  * ARCHIVED - User is no longer active. 
   
  * COMPROMISED - User is disabled due to a potential security threat. 
   
  * UNKNOWN - User status is not known. 
   

  

  

MFAOptions -> (list)

  

  Specifies the options for MFA (e.g., email or phone number).

  

  (structure)

    

    Specifies the different settings for multi-factor authentication (MFA).

    

    DeliveryMedium -> (string)

      

      The delivery medium (email message or SMS message) to send the MFA code.

      

      

    AttributeName -> (string)

      

      The attribute name of the MFA option type.

      

      

    

  

