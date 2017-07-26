[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp respond-to-auth-challenge:


*************************
respond-to-auth-challenge
*************************



===========
Description
===========



Responds to the authentication challenge.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/RespondToAuthChallenge>`_


========
Synopsis
========

::

    respond-to-auth-challenge
  --client-id <value>
  --challenge-name <value>
  [--session <value>]
  [--challenge-responses <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-id`` (string)


  The app client ID.

  

``--challenge-name`` (string)


  The challenge name. For more information, see `initiate-auth <API_InitiateAuth.html>`_ .

   

   ``ADMIN_NO_SRP_AUTH`` is not a valid value.

  

  Possible values:

  
  *   ``SMS_MFA``

  
  *   ``PASSWORD_VERIFIER``

  
  *   ``CUSTOM_CHALLENGE``

  
  *   ``DEVICE_SRP_AUTH``

  
  *   ``DEVICE_PASSWORD_VERIFIER``

  
  *   ``ADMIN_NO_SRP_AUTH``

  
  *   ``NEW_PASSWORD_REQUIRED``

  

  

``--session`` (string)


  The session which should be passed both ways in challenge-response calls to the service. If ``initiate-auth`` or ``respond-to-auth-challenge`` API call determines that the caller needs to go through another challenge, they return a session with other challenge parameters. This session should be passed as it is to the next ``respond-to-auth-challenge`` API call.

  

``--challenge-responses`` (map)


  The challenge responses. These are inputs corresponding to the value of ``ChallengeName`` , for example:

   

   
  * ``SMS_MFA`` : ``SMS_MFA_CODE`` , ``USERNAME`` , ``SECRET_HASH`` (if app client is configured with client secret). 
   
  * ``PASSWORD_VERIFIER`` : ``PASSWORD_CLAIM_SIGNATURE`` , ``PASSWORD_CLAIM_SECRET_BLOCK`` , ``TIMESTAMP`` , ``USERNAME`` , ``SECRET_HASH`` (if app client is configured with client secret). 
   
  * ``NEW_PASSWORD_REQUIRED`` : ``NEW_PASSWORD`` , any other required attributes, ``USERNAME`` , ``SECRET_HASH`` (if app client is configured with client secret).  
   

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChallengeName -> (string)

  

  The challenge name. For more information, see `initiate-auth <API_InitiateAuth.html>`_ .

  

  

Session -> (string)

  

  The session which should be passed both ways in challenge-response calls to the service. If the `initiate-auth <API_InitiateAuth.html>`_ or `respond-to-auth-challenge <API_RespondToAuthChallenge.html>`_ API call determines that the caller needs to go through another challenge, they return a session with other challenge parameters. This session should be passed as it is to the next ``respond-to-auth-challenge`` API call.

  

  

ChallengeParameters -> (map)

  

  The challenge parameters. For more information, see `initiate-auth <API_InitiateAuth.html>`_ .

  

  key -> (string)

    

    

  value -> (string)

    

    

  

AuthenticationResult -> (structure)

  

  The result returned by the server in response to the request to respond to the authentication challenge.

  

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

      

      

    

  

