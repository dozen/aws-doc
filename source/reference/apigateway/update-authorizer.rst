[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-authorizer:


*****************
update-authorizer
*****************



===========
Description
===========



Updates an existing  Authorizer resource.



========
Synopsis
========

::

    update-authorizer
  --rest-api-id <value>
  --authorizer-id <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The  RestApi identifier for the  Authorizer resource.

  

``--authorizer-id`` (string)


  The identifier of the  Authorizer resource.

  

``--patch-operations`` (list)


  A list of operations describing the updates to apply to the specified resource. The patches are applied in the order specified in the list.

  



Shorthand Syntax::

    op=string,path=string,value=string,from=string ...




JSON Syntax::

  [
    {
      "op": "add"|"remove"|"replace"|"move"|"copy"|"test",
      "path": "string",
      "value": "string",
      "from": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

id -> (string)

  

  The identifier for the authorizer resource.

  

  

name -> (string)

  

  [Required] The name of the authorizer.

  

  

type -> (string)

  

  [Required] The type of the authorizer. Currently, the only valid type is TOKEN.

  

  

authorizerUri -> (string)

  

  [Required] Specifies the authorizer's Uniform Resource Identifier (URI). For TOKEN authorizers, this must be a well-formed Lambda function URI. The URI should be of the form ``arn:aws:apigateway:{region}:lambda:path/{service_api}`` . ``Region`` is used to determine the right endpoint. In this case, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` . For Lambda functions, this is usually of the form /2015-03-31/functions/[FunctionARN]/invocations

  

  

authorizerCredentials -> (string)

  

  Specifies the credentials required for the authorizer, if any. Two options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To use resource-based permissions on the Lambda function, specify null.

  

  

identitySource -> (string)

  

  [Required] The source of the identity in an incoming request. For TOKEN authorizers, this value is a mapping expression with the same syntax as integration parameter mappings. The only valid source for tokens is 'header', so the expression should match 'method.request.header.[headerName]'. The value of the header '[headerName]' will be interpreted as the incoming token.

  

  

identityValidationExpression -> (string)

  

  A validation expression for the incoming identity. For TOKEN authorizers, this value should be a regular expression. The incoming token from the client is matched against this expression, and will proceed if the token matches. If the token doesn't match, the client receives a 401 Unauthorized response.

  

  

authorizerResultTtlInSeconds -> (integer)

  

  The TTL in seconds of cached authorizer results. If greater than 0, API Gateway will cache authorizer responses. If this field is not set, the default value is 300. The maximum value is 3600, or 1 hour.

  

  

