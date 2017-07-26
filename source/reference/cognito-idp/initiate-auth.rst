[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp initiate-auth:


*************
initiate-auth
*************



===========
Description
===========



Initiates the authentication flow.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/InitiateAuth>`_


========
Synopsis
========

::

    initiate-auth
  --auth-flow <value>
  [--auth-parameters <value>]
  [--client-metadata <value>]
  --client-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auth-flow`` (string)


  The authentication flow for this call to execute. The API action will depend on this value. For example: 

   

   
  * ``REFRESH_TOKEN_AUTH`` will take in a valid refresh token and return new tokens. 
   
  * ``USER_SRP_AUTH`` will take in ``USERNAME`` and ``SRP_A`` and return the SRP variables to be used for next challenge execution. 
   

   

  Valid values include:

   

   
  * ``USER_SRP_AUTH`` : Authentication flow for the Secure Remote Password (SRP) protocol. 
   
  * ``REFRESH_TOKEN_AUTH`` /``REFRESH_TOKEN`` : Authentication flow for refreshing the access token and ID token by supplying a valid refresh token. 
   
  * ``CUSTOM_AUTH`` : Custom authentication flow. 
   

   

   ``ADMIN_NO_SRP_AUTH`` is not a valid value.

  

  Possible values:

  
  *   ``USER_SRP_AUTH``

  
  *   ``REFRESH_TOKEN_AUTH``

  
  *   ``REFRESH_TOKEN``

  
  *   ``CUSTOM_AUTH``

  
  *   ``ADMIN_NO_SRP_AUTH``

  

  

``--auth-parameters`` (map)


  The authentication parameters. These are inputs corresponding to the ``AuthFlow`` that you are invoking. The required values depend on the value of ``AuthFlow`` :

   

   
  * For ``USER_SRP_AUTH`` : ``USERNAME`` (required), ``SRP_A`` (required), ``SECRET_HASH`` (required if the app client is configured with a client secret), ``DEVICE_KEY``   
   
  * For ``REFRESH_TOKEN_AUTH/REFRESH_TOKEN`` : ``USERNAME`` (required), ``SECRET_HASH`` (required if the app client is configured with a client secret), ``REFRESH_TOKEN`` (required), ``DEVICE_KEY``   
   
  * For ``CUSTOM_AUTH`` : ``USERNAME`` (required), ``SECRET_HASH`` (if app client is configured with client secret), ``DEVICE_KEY``   
   

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--client-metadata`` (map)


  This is a random key-value pair map which can contain any key and will be passed to your PreAuthentication Lambda trigger as-is. It can be used to implement additional validations around authentication.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--client-id`` (string)


  The app client ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChallengeName -> (string)

  

  The name of the challenge which you are responding to with this call. This is returned to you in the ``admin-initiate-auth`` response if you need to pass another challenge.

   

  Valid values include the following. Note that all of these challenges require ``USERNAME`` and ``SECRET_HASH`` (if applicable) in the parameters.

   

   
  * ``SMS_MFA`` : Next challenge is to supply an ``SMS_MFA_CODE`` , delivered via SMS. 
   
  * ``PASSWORD_VERIFIER`` : Next challenge is to supply ``PASSWORD_CLAIM_SIGNATURE`` , ``PASSWORD_CLAIM_SECRET_BLOCK`` , and ``TIMESTAMP`` after the client-side SRP calculations. 
   
  * ``CUSTOM_CHALLENGE`` : This is returned if your custom authentication flow determines that the user should pass another challenge before tokens are issued. 
   
  * ``DEVICE_SRP_AUTH`` : If device tracking was enabled on your user pool and the previous challenges were passed, this challenge is returned so that Amazon Cognito can start tracking this device. 
   
  * ``DEVICE_PASSWORD_VERIFIER`` : Similar to ``PASSWORD_VERIFIER`` , but for devices only. 
   
  * ``NEW_PASSWORD_REQUIRED`` : For users which are required to change their passwords after successful first login. This challenge should be passed with ``NEW_PASSWORD`` and any other required attributes. 
   

  

  

Session -> (string)

  

  The session which should be passed both ways in challenge-response calls to the service. If the `initiate-auth <API_InitiateAuth.html>`_ or `respond-to-auth-challenge <API_RespondToAuthChallenge.html>`_ API call determines that the caller needs to go through another challenge, they return a session with other challenge parameters. This session should be passed as it is to the next ``respond-to-auth-challenge`` API call.

  

  

ChallengeParameters -> (map)

  

  The challenge parameters. These are returned to you in the ``initiate-auth`` response if you need to pass another challenge. The responses in this parameter should be used to compute inputs to the next call (``respond-to-auth-challenge`` ). 

   

  All challenges require ``USERNAME`` and ``SECRET_HASH`` (if applicable).

  

  key -> (string)

    

    

  value -> (string)

    

    

  

AuthenticationResult -> (structure)

  

  The result of the authentication response. This is only returned if the caller does not need to pass another challenge. If the caller does need to pass another challenge before it gets tokens, ``ChallengeName`` , ``ChallengeParameters`` , and ``Session`` are returned.

  

  AccessToken -> (string)

    

    The access token of the authentication result.

    

    

  ExpiresIn -> (integer)

    

    The expiration period of the authentication result.

    

    

  TokenType -> (string)

    

    The token type of the authentication result.

    

    

  RefreshToken -> (string)

    

    The refresh token of the authentication result.

    

    

  IdToken -> (string)

    

    The ID token of the authentication result.

    

    

  NewDeviceMetadata -> (structure)

    

    The new device metadata from an authentication result.

    

    DeviceKey -> (string)

      

      The device key.

      

      

    DeviceGroupKey -> (string)

      

      The device group key.

      

      

    

  

