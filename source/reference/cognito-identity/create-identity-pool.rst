[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity create-identity-pool:


********************
create-identity-pool
********************



===========
Description
===========



Creates a new identity pool. The identity pool is a store of user identity information that is specific to your AWS account. The limit on identity pools is 60 per account. The keys for ``SupportedLoginProviders`` are as follows: 

 
* Facebook: ``graph.facebook.com``  
 
* Google: ``accounts.google.com``  
 
* Amazon: ``www.amazon.com``  
 
* Twitter: ``api.twitter.com``  
 
* Digits: ``www.digits.com``  
 

You must use AWS Developer credentials to call this API.



========
Synopsis
========

::

    create-identity-pool
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


  The "domain" by which Cognito will refer to your users. This name acts as a placeholder that allows your backend and the Cognito service to communicate about the developer provider. For the ``developer-provider-name`` , you can use letters as well as period (``.`` ), underscore (``_`` ), and dash (``-`` ).

   

  Once you have set a developer provider name, you cannot change it. Please take care in setting this parameter.

  

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

    

    

  

