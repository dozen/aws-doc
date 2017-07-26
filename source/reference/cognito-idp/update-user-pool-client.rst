[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp update-user-pool-client:


***********************
update-user-pool-client
***********************



===========
Description
===========



Allows the developer to update the specified user pool client and password policy.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/UpdateUserPoolClient>`_


========
Synopsis
========

::

    update-user-pool-client
  --user-pool-id <value>
  --client-id <value>
  [--client-name <value>]
  [--refresh-token-validity <value>]
  [--read-attributes <value>]
  [--write-attributes <value>]
  [--explicit-auth-flows <value>]
  [--supported-identity-providers <value>]
  [--callback-urls <value>]
  [--logout-urls <value>]
  [--default-redirect-uri <value>]
  [--allowed-o-auth-flows <value>]
  [--allowed-o-auth-scopes <value>]
  [--allowed-o-auth-flows-user-pool-client | --no-allowed-o-auth-flows-user-pool-client]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool where you want to update the user pool client.

  

``--client-id`` (string)


  The ID of the client associated with the user pool.

  

``--client-name`` (string)


  The client name from the update user pool client request.

  

``--refresh-token-validity`` (integer)


  The time limit, in days, after which the refresh token is no longer valid and cannot be used.

  

``--read-attributes`` (list)


  The read-only attributes of the user pool.

  



Syntax::

  "string" "string" ...



``--write-attributes`` (list)


  The writeable attributes of the user pool.

  



Syntax::

  "string" "string" ...



``--explicit-auth-flows`` (list)


  Explicit authentication flows.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    ADMIN_NO_SRP_AUTH
    CUSTOM_AUTH_FLOW_ONLY





``--supported-identity-providers`` (list)


  A list of provider names for the identity providers that are supported on this client.

  



Syntax::

  "string" "string" ...



``--callback-urls`` (list)


  A list of allowed callback URLs for the identity providers.

  



Syntax::

  "string" "string" ...



``--logout-urls`` (list)


  A list ofallowed logout URLs for the identity providers.

  



Syntax::

  "string" "string" ...



``--default-redirect-uri`` (string)


  The default redirect URI. Must be in the ``CallbackURLs`` list.

  

``--allowed-o-auth-flows`` (list)


  Set to ``code`` to initiate a code grant flow, which provides an authorization code as the response. This code can be exchanged for access tokens with the token endpoint.

   

  Set to ``token`` to specify that the client should get the access token (and, optionally, ID token, based on scopes) directly.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    code
    implicit
    client_credentials





``--allowed-o-auth-scopes`` (list)


  A list of allowed ``OAuth`` scopes. Currently supported values are ``"phone"`` , ``"email"`` , ``"openid"`` , and ``"Cognito"`` .

  



Syntax::

  "string" "string" ...



``--allowed-o-auth-flows-user-pool-client`` | ``--no-allowed-o-auth-flows-user-pool-client`` (boolean)


  Set to TRUE if the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

UserPoolClient -> (structure)

  

  The user pool client value from the response from the server when an update user pool client request is made.

  

  UserPoolId -> (string)

    

    The user pool ID for the user pool client.

    

    

  ClientName -> (string)

    

    The client name from the user pool request of the client type.

    

    

  ClientId -> (string)

    

    The ID of the client associated with the user pool.

    

    

  ClientSecret -> (string)

    

    The client secret from the user pool request of the client type.

    

    

  LastModifiedDate -> (timestamp)

    

    The date the user pool client was last modified.

    

    

  CreationDate -> (timestamp)

    

    The date the user pool client was created.

    

    

  RefreshTokenValidity -> (integer)

    

    The time limit, in days, after which the refresh token is no longer valid and cannot be used.

    

    

  ReadAttributes -> (list)

    

    The Read-only attributes.

    

    (string)

      

      

    

  WriteAttributes -> (list)

    

    The writeable attributes.

    

    (string)

      

      

    

  ExplicitAuthFlows -> (list)

    

    The explicit authentication flows.

    

    (string)

      

      

    

  SupportedIdentityProviders -> (list)

    

    A list of provider names for the identity providers that are supported on this client.

    

    (string)

      

      

    

  CallbackURLs -> (list)

    

    A list of allowed callback URLs for the identity providers.

    

    (string)

      

      

    

  LogoutURLs -> (list)

    

    A list ofallowed logout URLs for the identity providers.

    

    (string)

      

      

    

  DefaultRedirectURI -> (string)

    

    The default redirect URI. Must be in the ``CallbackURLs`` list.

    

    

  AllowedOAuthFlows -> (list)

    

    Set to ``code`` to initiate a code grant flow, which provides an authorization code as the response. This code can be exchanged for access tokens with the token endpoint.

     

    Set to ``token`` to specify that the client should get the access token (and, optionally, ID token, based on scopes) directly.

    

    (string)

      

      

    

  AllowedOAuthScopes -> (list)

    

    A list of allowed ``OAuth`` scopes. Currently supported values are ``"phone"`` , ``"email"`` , ``"openid"`` , and ``"Cognito"`` .

    

    (string)

      

      

    

  AllowedOAuthFlowsUserPoolClient -> (boolean)

    

    Set to TRUE if the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.

    

    

  

