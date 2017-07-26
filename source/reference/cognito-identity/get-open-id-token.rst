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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/GetOpenIdToken>`_


========
Synopsis
========

::

    get-open-id-token
  --identity-id <value>
  [--logins <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-id`` (string)


  A unique identifier in the format REGION:GUID.

  

``--logins`` (map)


  A set of optional name-value pairs that map provider names to provider tokens. When using graph.facebook.com and www.amazon.com, supply the access_token returned from the provider's authflow. For accounts.google.com, an Amazon Cognito Identity Provider, or any other OpenId Connect provider, always include the ``id_token`` .

  



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

IdentityId -> (string)

  

  A unique identifier in the format REGION:GUID. Note that the identity-id returned may not match the one passed on input.

  

  

Token -> (string)

  

  An OpenID token, valid for 15 minutes.

  

  

