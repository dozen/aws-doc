[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-integration:


***************
get-integration
***************



===========
Description
===========



Represents a get integration.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetIntegration>`_


========
Synopsis
========

::

    get-integration
  --rest-api-id <value>
  --resource-id <value>
  --http-method <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--resource-id`` (string)


  Specifies a get integration request's resource identifier

  

``--http-method`` (string)


  Specifies a get integration request's HTTP method.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the integration configuration for a HTTP method defined under a REST API's resource**

Command::

  aws apigateway get-integration --rest-api-id 1234123412 --resource-id y9h6rt --http-method GET

Output::

  {
      "httpMethod": "POST", 
      "integrationResponses": {
          "200": {
              "responseTemplates": {
                  "application/json": null
              }, 
              "statusCode": "200"
          }
      }, 
      "cacheKeyParameters": [], 
      "type": "AWS", 
      "uri": "arn:aws:apigateway:us-west-2:lambda:path/2015-03-31/functions/arn:aws:lambda:us-west-2:123412341234:function:My_Function/invocations", 
      "cacheNamespace": "y9h6rt"
  }



======
Output
======

type -> (string)

  

  Specifies the integration's type. The valid value is ``HTTP`` for integrating with an HTTP back end, ``AWS`` for any AWS service endpoints, ``MOCK`` for testing without actually invoking the back end, ``HTTP_PROXY`` for integrating with the HTTP proxy integration, or ``AWS_PROXY`` for integrating with the Lambda proxy integration type.

  

  

httpMethod -> (string)

  

  Specifies the integration's HTTP method type.

  

  

uri -> (string)

  

  Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification <https://en.wikipedia.org/wiki/Uniform_Resource_Identifier>`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

  

  

credentials -> (string)

  

  Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

  

  

requestParameters -> (map)

  

  A key-value map specifying request parameters that are passed from the method request to the back end. The key is an integration request parameter name and the associated value is a method request parameter value or static value that must be enclosed within single quotes and pre-encoded as required by the back end. The method request parameter value must match the pattern of ``method.request.{location}.{name}`` , where ``location`` is ``querystring`` , ``path`` , or ``header`` and ``name`` must be a valid and unique method request parameter name.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

requestTemplates -> (map)

  

  Represents a map of Velocity templates that are applied on the request payload based on the value of the Content-Type header sent by the client. The content type value is the key in this map, and the template (as a String) is the value.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

passthroughBehavior -> (string)

   

  Specifies how the method request body of an unmapped content type will be passed through the integration request to the back end without transformation. A content type is unmapped if no mapping template is defined in the integration or the content type does not match any of the mapped content types, as specified in ``requestTemplates`` . There are three valid values: ``WHEN_NO_MATCH`` , ``WHEN_NO_TEMPLATES`` , and ``NEVER`` . 

   

   
  * ``WHEN_NO_MATCH`` passes the method request body through the integration request to the back end without transformation when the method request content type does not match any content type associated with the mapping templates defined in the integration request. 
   
  * ``WHEN_NO_TEMPLATES`` passes the method request body through the integration request to the back end without transformation when no mapping template is defined in the integration request. If a template is defined when this option is selected, the method request of an unmapped content-type will be rejected with an HTTP ``415 Unsupported Media Type`` response. 
   
  * ``NEVER`` rejects the method request with an HTTP ``415 Unsupported Media Type`` response when either the method request content type does not match any content type associated with the mapping templates defined in the integration request or no mapping template is defined in the integration request. 
   

   

  

contentHandling -> (string)

  

  Specifies how to handle request payload content type conversions. Supported values are ``CONVERT_TO_BINARY`` and ``CONVERT_TO_TEXT`` , with the following behaviors:

   

   
  * ``CONVERT_TO_BINARY`` : Converts a request payload from a Base64-encoded string to the corresponding binary blob.
   
  * ``CONVERT_TO_TEXT`` : Converts a request payload from a binary blob to a Base64-encoded string.
   

   

  If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the ``passthroughBehaviors`` is configured to support payload pass-through.

  

  

cacheNamespace -> (string)

  

  Specifies the integration's cache namespace.

  

  

cacheKeyParameters -> (list)

  

  Specifies the integration's cache key parameters.

  

  (string)

    

    

  

integrationResponses -> (map)

  

  Specifies the integration's responses.

    

  

   Example: Get integration responses of a method Request 

  

   ``GET /restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200 HTTP/1.1 Content-Type: application/json Host: apigateway.us-east-1.amazonaws.com X-Amz-Date: 20160607T191449Z Authorization: AWS4-HMAC-SHA256 Credential={access_key_ID}/20160607/us-east-1/apigateway/aws4_request, SignedHeaders=content-type;host;x-amz-date, Signature={sig4_hash}``  Response 

  The successful response returns ``200 OK`` status and a payload as follows:

   ``{ "_links": { "curies": { "href": "http://docs.aws.amazon.com/apigateway/latest/developerguide/restapi-integration-response-{rel}.html", "name": "integrationresponse", "templated": true }, "self": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200", "title": "200" }, "integrationresponse:delete": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" }, "integrationresponse:update": { "href": "/restapis/fugvjdxtri/resources/3kzxbg5sa2/methods/GET/integration/responses/200" } }, "responseParameters": { "method.response.header.Content-Type": "'application/xml'" }, "responseTemplates": { "application/json": "$util.urlDecode(\"%3CkinesisStreams%3E#foreach($stream in $input.path('$.StreamNames'))%3Cstream%3E%3Cname%3E$stream%3C/name%3E%3C/stream%3E#end%3C/kinesisStreams%3E\")\n" }, "statusCode": "200" }``  

  

     `Creating an API <http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-create-api.html>`_  

  key -> (string)

    

    

  value -> (structure)

    

    Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the back-end response.

      `Creating an API <http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-create-api.html>`_  

    statusCode -> (string)

      

      Specifies the status code that is used to map the integration response to an existing  MethodResponse .

      

      

    selectionPattern -> (string)

      

      Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the back end. For example, if the success response returns nothing and the error response returns some string, you could use the ``.+`` regex to match error response. However, make sure that the error response does not contain any newline (``\n`` ) character in such cases. If the back end is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS back ends, the HTTP status code is matched.

      

      

    responseParameters -> (map)

      

      A key-value map specifying response parameters that are passed to the method response from the back end. The key is a method response header parameter name and the mapped value is an integration response header value, a static value enclosed within a pair of single quotes, or a JSON expression from the integration response body. The mapping key must match the pattern of ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. The mapped non-static value must match the pattern of ``integration.response.header.{name}`` or ``integration.response.body.{JSON-expression}`` , where ``name`` is a valid and unique response header name and ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    responseTemplates -> (map)

      

      Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    contentHandling -> (string)

      

      Specifies how to handle response payload content type conversions. Supported values are ``CONVERT_TO_BINARY`` and ``CONVERT_TO_TEXT`` , with the following behaviors:

       

       
      * ``CONVERT_TO_BINARY`` : Converts a response payload from a Base64-encoded string to the corresponding binary blob.
       
      * ``CONVERT_TO_TEXT`` : Converts a response payload from a binary blob to a Base64-encoded string.
       

       

      If this property is not defined, the response payload will be passed through from the integration response to the method response without modification.

      

      

    

  

