[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity describe-identity-pool:


**********************
describe-identity-pool
**********************



===========
Description
===========



Gets details about a particular identity pool, including the pool name, ID description, creation date, and current number of users.

 

You must use AWS Developer credentials to call this API.



========
Synopsis
========

::

    describe-identity-pool
  --identity-pool-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-pool-id`` (string)
An identity pool ID in the format REGION:GUID.

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

    

    

  

