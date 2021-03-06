[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-authorizer:


*****************
create-authorizer
*****************



===========
Description
===========



Adds a new  Authorizer resource to an existing  RestApi resource.

 `AWS CLI <http://docs.aws.amazon.com/cli/latest/reference/apigateway/create-authorizer.html>`_ 

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/CreateAuthorizer>`_


========
Synopsis
========

::

    create-authorizer
  --rest-api-id <value>
  --name <value>
  --type <value>
  [--provider-arns <value>]
  [--auth-type <value>]
  [--authorizer-uri <value>]
  [--authorizer-credentials <value>]
  --identity-source <value>
  [--identity-validation-expression <value>]
  [--authorizer-result-ttl-in-seconds <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--name`` (string)


  [Required] The name of the authorizer.

  

``--type`` (string)


  [Required] The type of the authorizer.

  

  Possible values:

  
  *   ``TOKEN``

  
  *   ``COGNITO_USER_POOLS``

  

  

``--provider-arns`` (list)


  A list of the Cognito Your User Pool authorizer's provider ARNs.

  



Syntax::

  "string" "string" ...



``--auth-type`` (string)


  Optional customer-defined field, used in Swagger imports/exports. Has no functional impact.

  

``--authorizer-uri`` (string)


  [Required] Specifies the authorizer's Uniform Resource Identifier (URI).

  

``--authorizer-credentials`` (string)


  Specifies the credentials required for the authorizer, if any.

  

``--identity-source`` (string)


  [Required] The source of the identity in an incoming request.

  

``--identity-validation-expression`` (string)


  A validation expression for the incoming identity.

  

``--authorizer-result-ttl-in-seconds`` (integer)


  The TTL of cached authorizer results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a token based API Gateway Custom Authorizer for the API**

Command::

  aws apigateway create-authorizer --rest-api-id 1234123412 --name 'First_Token_Custom_Authorizer' --type TOKEN --authorizer-uri 'arn:aws:apigateway:us-west-2:lambda:path/2015-03-31/functions/arn:aws:lambda:us-west-2:123412341234:function:customAuthFunction/invocations' --identity-source 'method.request.header.Authorization' --authorizer-result-ttl-in-seconds 300

Output::

  {
      "authType": "custom", 
      "name": "First_Token_Custom_Authorizer", 
      "authorizerUri": "arn:aws:apigateway:us-west-2:lambda:path/2015-03-31/functions/arn:aws:lambda:us-west-2:123412341234:function:customAuthFunction/invocations", 
      "authorizerResultTtlInSeconds": 300, 
      "identitySource": "method.request.header.Authorization", 
      "type": "TOKEN", 
      "id": "z40xj0"
  }

**To create a Cognito User Pools based API Gateway Custom Authorizer for the API**

Command::

  aws apigateway create-authorizer --rest-api-id 1234123412 --name 'First_Cognito_Custom_Authorizer' --type COGNITO_USER_POOLS --provider-arns 'arn:aws:cognito-idp:us-east-1:123412341234:userpool/us-east-1_aWcZeQbuD' --identity-source 'method.request.header.Authorization'

Output::

  {
      "authType": "cognito_user_pools", 
      "identitySource": "method.request.header.Authorization", 
      "name": "First_Cognito_Custom_Authorizer", 
      "providerARNs": [
          "arn:aws:cognito-idp:us-east-1:342398297714:userpool/us-east-1_qWbZzQhzE"
      ], 
      "type": "COGNITO_USER_POOLS", 
      "id": "5yid1t"
  }


======
Output
======

id -> (string)

  

  The identifier for the authorizer resource.

  

  

name -> (string)

  

  [Required] The name of the authorizer.

  

  

type -> (string)

  

  [Required] The type of the authorizer. Currently, the valid type is ``TOKEN`` for a Lambda function or ``COGNITO_USER_POOLS`` for an Amazon Cognito user pool.

  

  

providerARNs -> (list)

  

  A list of the provider ARNs of the authorizer. For an ``TOKEN`` authorizer, this is not defined. For authorizers of the ``COGNITO_USER_POOLS`` type, each element corresponds to a user pool ARN of this format: ``arn:aws:cognito-idp:{region}:{account_id}:userpool/{user_pool_id}`` . 

  

  (string)

    

    

  

authType -> (string)

  

  Optional customer-defined field, used in Swagger imports/exports. Has no functional impact.

  

  

authorizerUri -> (string)

  

  [Required] Specifies the authorizer's Uniform Resource Identifier (URI). For ``TOKEN`` authorizers, this must be a well-formed Lambda function URI, for example, ``arn:aws:apigateway:us-west-2:lambda:path/2015-03-31/functions/arn:aws:lambda:us-west-2:{account_id}:function:{lambda_function_name}/invocations`` . In general, the URI has this form ``arn:aws:apigateway:{region}:lambda:path/{service_api}`` , where ``{region}`` is the same as the region hosting the Lambda function, ``path`` indicates that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` . For Lambda functions, this is usually of the form /2015-03-31/functions/[FunctionARN]/invocations.

  

  

authorizerCredentials -> (string)

  

  Specifies the credentials required for the authorizer, if any. Two options are available. To specify an IAM role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To use resource-based permissions on the Lambda function, specify null.

  

  

identitySource -> (string)

  

  [Required] The source of the identity in an incoming request. For a ``TOKEN`` authorizer, this value is a mapping expression with the same syntax as integration parameter mappings. The only valid source for tokens is 'header', so the expression should match 'method.request.header.[headerName]'. The value of the header '[headerName]' will be interpreted as the incoming token. For ``COGNITO_USER_POOLS`` authorizers, this property is used.

  

  

identityValidationExpression -> (string)

  

  A validation expression for the incoming identity. For ``TOKEN`` authorizers, this value should be a regular expression. The incoming token from the client is matched against this expression, and will proceed if the token matches. If the token doesn't match, the client receives a 401 Unauthorized response.

  

  

authorizerResultTtlInSeconds -> (integer)

  

  The TTL in seconds of cached authorizer results. If greater than 0, API Gateway will cache authorizer responses. If this field is not set, the default value is 300. The maximum value is 3600, or 1 hour.

  

  

