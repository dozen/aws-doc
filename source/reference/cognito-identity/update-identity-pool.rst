[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity update-identity-pool:


********************
update-identity-pool
********************



===========
Description
===========



Updates a user pool.

 

You must use AWS Developer credentials to call this API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/UpdateIdentityPool>`_


========
Synopsis
========

::

    update-identity-pool
  --identity-pool-id <value>
  --identity-pool-name <value>
  --allow-unauthenticated-identities | --no-allow-unauthenticated-identities
  [--supported-login-providers <value>]
  [--developer-provider-name <value>]
  [--open-id-connect-provider-arns <value>]
  [--cognito-identity-providers <value>]
  [--saml-provider-arns <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--identity-pool-name`` (string)


  A string that you provide.

  

``--allow-unauthenticated-identities`` | ``--no-allow-unauthenticated-identities`` (boolean)


  TRUE if the identity pool supports unauthenticated logins.

  

``--supported-login-providers`` (map)


  Optional key:value pairs mapping provider names to provider app IDs.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--developer-provider-name`` (string)


  The "domain" by which Cognito will refer to your users.

  

``--open-id-connect-provider-arns`` (list)


  A list of OpendID Connect provider ARNs.

  



Syntax::

  "string" "string" ...



``--cognito-identity-providers`` (list)


  A list representing an Amazon Cognito Identity User Pool and its client ID.

  



Shorthand Syntax::

    ProviderName=string,ClientId=string,ServerSideTokenCheck=boolean ...




JSON Syntax::

  [
    {
      "ProviderName": "string",
      "ClientId": "string",
      "ServerSideTokenCheck": true|false
    }
    ...
  ]



``--saml-provider-arns`` (list)


  An array of Amazon Resource Names (ARNs) of the SAML provider for your identity pool.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityPoolId -> (string)

  

  An identity pool ID in the format REGION:GUID.

  

  

IdentityPoolName -> (string)

  

  A string that you provide.

  

  

AllowUnauthenticatedIdentities -> (boolean)

  

  TRUE if the identity pool supports unauthenticated logins.

  

  

SupportedLoginProviders -> (map)

  

  Optional key:value pairs mapping provider names to provider app IDs.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

DeveloperProviderName -> (string)

  

  The "domain" by which Cognito will refer to your users.

  

  

OpenIdConnectProviderARNs -> (list)

  

  A list of OpendID Connect provider ARNs.

  

  (string)

    

    

  

CognitoIdentityProviders -> (list)

  

  A list representing an Amazon Cognito Identity User Pool and its client ID.

  

  (structure)

    

    A provider representing an Amazon Cognito Identity User Pool and its client ID.

    

    ProviderName -> (string)

      

      The provider name for an Amazon Cognito Identity User Pool. For example, ``cognito-idp.us-east-1.amazonaws.com/us-east-1_123456789`` .

      

      

    ClientId -> (string)

      

      The client ID for the Amazon Cognito Identity User Pool.

      

      

    ServerSideTokenCheck -> (boolean)

      

      TRUE if server-side token validation is enabled for the identity provider’s token.

      

      

    

  

SamlProviderARNs -> (list)

  

  An array of Amazon Resource Names (ARNs) of the SAML provider for your identity pool.

  

  (string)

    

    

  

