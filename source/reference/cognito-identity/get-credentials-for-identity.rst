[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity get-credentials-for-identity:


****************************
get-credentials-for-identity
****************************



===========
Description
===========



Returns credentials for the provided identity ID. Any provided logins will be validated against supported login providers. If the token is for cognito-identity.amazonaws.com, it will be passed through to AWS Security Token Service with the appropriate role for the token.

 

This is a public API. You do not need any credentials to call this API.



========
Synopsis
========

::

    get-credentials-for-identity
  --identity-id <value>
  [--logins <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-id`` (string)


  A unique identifier in the format REGION:GUID.

  

``--logins`` (map)


  A set of optional name-value pairs that map provider names to provider tokens.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

IdentityId -> (string)

  

  A unique identifier in the format REGION:GUID.

  

  

Credentials -> (structure)

  

  Credentials for the provided identity ID.

  

  AccessKeyId -> (string)

    

    The Access Key portion of the credentials.

    

    

  SecretKey -> (string)

    

    The Secret Access Key portion of the credentials

    

    

  SessionToken -> (string)

    

    The Session Token portion of the credentials

    

    

  Expiration -> (timestamp)

    

    The date at which these credentials will expire.

    

    

  

