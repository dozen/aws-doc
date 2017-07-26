[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-gateway-responses:


*********************
get-gateway-responses
*********************



===========
Description
===========



Gets the  GatewayResponses collection on the given  RestApi . If an API developer has not added any definitions for gateway responses, the result will be the Amazon API Gateway-generated default  GatewayResponses collection for the supported response types.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetGatewayResponses>`_


========
Synopsis
========

::

    get-gateway-responses
  --rest-api-id <value>
  [--position <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--position`` (string)


  The current pagination position in the paged result set. The  GatewayResponse collection does not support pagination and the position does not apply here.

  

``--limit`` (integer)


  The maximum number of returned results per page. The  GatewayResponses collection does not support pagination and the limit does not apply here.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

position -> (string)

  

  

items -> (list)

  

  Returns the entire collection, because of no pagination support.

  

  (structure)

    

    A gateway response of a given response type and status code, with optional response parameters and mapping templates.

     For more information about valid gateway response types, see `Gateway Response Types Supported by Amazon API Gateway <http://docs.aws.amazon.com/apigateway/latest/developerguide/supported-gateway-response-types.html>`_   Example: Get a Gateway Response of a given response type Request 

    This example shows how to get a gateway response of the ``MISSING_AUTHNETICATION_TOKEN`` type.

     ``GET /restapis/o81lxisefl/gatewayresponses/MISSING_AUTHENTICATION_TOKEN HTTP/1.1 Host: beta-apigateway.us-east-1.amazonaws.com Content-Type: application/json X-Amz-Date: 20170503T202516Z Authorization: AWS4-HMAC-SHA256 Credential={access-key-id}/20170503/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature=1b52460e3159c1a26cff29093855d50ea141c1c5b937528fecaf60f51129697a Cache-Control: no-cache Postman-Token: 3b2a1ce9-c848-2e26-2e2f-9c2caefbed45``  

    The response type is specified as a URL path.

     Response 

    The successful operation returns the ``200 OK`` status code and a payload similar to the following:

     ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-gatewayresponse-{rel}.html", "name": "gatewayresponse", "templated": true }, "self": { "href": "/restapis/o81lxisefl/gatewayresponses/MISSING_AUTHENTICATION_TOKEN" }, "gatewayresponse:delete": { "href": "/restapis/o81lxisefl/gatewayresponses/MISSING_AUTHENTICATION_TOKEN" }, "gatewayresponse:put": { "href": "/restapis/o81lxisefl/gatewayresponses/{response_type}", "templated": true }, "gatewayresponse:update": { "href": "/restapis/o81lxisefl/gatewayresponses/MISSING_AUTHENTICATION_TOKEN" } }, "defaultResponse": false, "responseParameters": { "gatewayresponse.header.x-request-path": "method.request.path.petId", "gatewayresponse.header.Access-Control-Allow-Origin": "a.b.c", "gatewayresponse.header.x-request-query": "method.request.querystring.q", "gatewayresponse.header.x-request-header": "method.request.header.Accept" }, "responseTemplates": { "application/json": "{\n \"message\": $context.error.messageString,\n \"type\": \"$context.error.responseType\",\n \"stage\": \"$context.stage\",\n \"resourcePath\": \"$context.resourcePath\",\n \"stageVariables.a\": \"$stageVariables.a\",\n \"statusCode\": \"404\"\n}" }, "responseType": "MISSING_AUTHENTICATION_TOKEN", "statusCode": "404" }``  

    

        `Customize Gateway Responses <http://docs.aws.amazon.com/apigateway/latest/developerguide/customize-gateway-responses.html>`_  

    responseType -> (string)

      

      The response type of the associated  GatewayResponse . Valid values are 

      
      * ACCESS_DENIED
      
      * API_CONFIGURATION_ERROR
      
      * AUTHORIZER_FAILURE
      
      * AUTHORIZER_CONFIGURATION_ERROR
      
      * BAD_REQUEST_PARAMETERS
      
      * BAD_REQUEST_BODY
      
      * DEFAULT_4XX
      
      * DEFAULT_5XX
      
      * EXPIRED_TOKEN
      
      * INVALID_SIGNATURE
      
      * INTEGRATION_FAILURE
      
      * INTEGRATION_TIMEOUT
      
      * INVALID_API_KEY
      
      * MISSING_AUTHENTICATION_TOKEN
      
      * QUOTA_EXCEEDED
      
      * REQUEST_TOO_LARGE
      
      * RESOURCE_NOT_FOUND
      
      * THROTTLED
      
      * UNAUTHORIZED
      
      * UNSUPPORTED_MEDIA_TYPES
      

       

      

      

    statusCode -> (string)

      

      The HTTP status code for this  GatewayResponse .

      

      

    responseParameters -> (map)

      

      Response parameters (paths, query strings and headers) of the  GatewayResponse as a string-to-string map of key-value pairs.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    responseTemplates -> (map)

      

      Response templates of the  GatewayResponse as a string-to-string map of key-value pairs.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    defaultResponse -> (boolean)

      

      A Boolean flag to indicate whether this  GatewayResponse is the default gateway response (``true`` ) or not (``false`` ). A default gateway response is one generated by Amazon API Gateway without any customization by an API developer. 

      

      

    

  

