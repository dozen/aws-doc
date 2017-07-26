[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity get-open-id-token-for-developer-identity:


****************************************
get-open-id-token-for-developer-identity
****************************************



===========
Description
===========



Registers (or retrieves) a Cognito ``identity-id`` and an OpenID Connect token for a user authenticated by your backend authentication process. Supplying multiple logins will create an implicit linked account. You can only specify one developer provider as part of the ``Logins`` map, which is linked to the identity pool. The developer provider is the "domain" by which Cognito will refer to your users.

 

You can use ``get-open-id-token-for-developer-identity`` to create a new identity and to link new logins (that is, user credentials issued by a public provider or developer provider) to an existing identity. When you want to create a new identity, the ``identity-id`` should be null. When you want to associate a new login with an existing authenticated/unauthenticated identity, you can do so by providing the existing ``identity-id`` . This API will create the identity in the specified ``identity-pool-id`` .

 

You must use AWS Developer credentials to call this API.



========
Synopsis
========

::

    get-open-id-token-for-developer-identity
  --identity-pool-id <value>
  [--identity-id <value>]
  --logins <value>
  [--token-duration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--identity-id`` (string)


  A unique identifier in the format REGION:GUID.

  

``--logins`` (map)


  A set of optional name-value pairs that map provider names to provider tokens. Each name-value pair represents a user from a public provider or developer provider. If the user is from a developer provider, the name-value pair will follow the syntax ``"developer_provider_name": "developer_user_identifier"`` . The developer provider is the "domain" by which Cognito will refer to your users; you provided this domain while creating/updating the identity pool. The developer user identifier is an identifier from your backend that uniquely identifies a user. When you create an identity pool, you can specify the supported logins.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--token-duration`` (long)


  The expiration time of the token, in seconds. You can specify a custom expiration time for the token so that you can cache it. If you don't provide an expiration time, the token is valid for 15 minutes. You can exchange the token with Amazon STS for temporary AWS credentials, which are valid for a maximum of one hour. The maximum token duration you can set is 24 hours. You should take care in setting the expiration time for a token, as there are significant security implications: an attacker could use a leaked token to access your AWS resources for the token's duration.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

IdentityId -> (string)

  

  A unique identifier in the format REGION:GUID.

  

  

Token -> (string)

  

  An OpenID token.

  

  

