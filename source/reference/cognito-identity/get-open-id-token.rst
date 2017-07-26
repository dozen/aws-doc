[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity get-open-id-token:


*****************
get-open-id-token
*****************



===========
Description
===========



Gets an OpenID token, using a known Cognito ID. This known Cognito ID is returned by  get-id . You can optionally add additional logins for the identity. Supplying multiple logins creates an implicit link.

 

The OpenId token is valid for 15 minutes.

 

This is a public API. You do not need any credentials to call this API.



========
Synopsis
========

::

    get-open-id-token
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
A set of optional name-value pairs that map provider names to provider tokens. When using graph.facebook.com and www.amazon.com, supply the access_token returned from the provider's authflow. For accounts.google.com or any other OpenId Connect provider, always include the id_token.



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

  A unique identifier in the format REGION:GUID. Note that the identity-id returned may not match the one passed on input.

  

Token -> (string)

  An OpenID token, valid for 15 minutes.

  

