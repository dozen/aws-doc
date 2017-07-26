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
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    

  

