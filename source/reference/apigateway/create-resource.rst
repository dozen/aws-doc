[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-resource:


***************
create-resource
***************



===========
Description
===========



Creates a  Resource resource.



========
Synopsis
========

::

    create-resource
  --rest-api-id <value>
  --parent-id <value>
  --path-part <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The identifier of the  RestApi for the resource. 

  

``--parent-id`` (string)


  The parent resource's identifier.

  

``--path-part`` (string)


  The last path segment for this resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

id -> (string)

  

  The resource's identifier.

  

  

parentId -> (string)

  

  The parent resource's identifier.

  

  

pathPart -> (string)

  

  The last path segment for this resource.

  

  

path -> (string)

  

  The full path for this resource.

  

  

resourceMethods -> (map)

  

  Map of methods for this resource, which is included only if requested using the **embed** option.

  

  key -> (string)

    

    

  value -> (structure)

    

    Represents a method.

    

    httpMethod -> (string)

      

      The HTTP method.

      

      

    authorizationType -> (string)

      

      The method's authorization type.

      

      

    authorizerId -> (string)

      

      Specifies the identifier of an  Authorizer to use on this Method. The authorizationType must be CUSTOM.

      

      

    apiKeyRequired -> (boolean)

      

      Specifies whether the method requires a valid  ApiKey .

      

      

    requestParameters -> (map)

      

      Represents request parameters that can be accepted by Amazon API Gateway. Request parameters are represented as a key/value map, with a source as the key and a Boolean flag as the value. The Boolean flag is used to specify whether the parameter is required. A source must match the pattern ``method.request.{location}.{name}`` , where ``location`` is either querystring, path, or header. ``name`` is a valid, unique parameter name. Sources specified here are available to the integration for mapping to integration request parameters or templates.

      

      key -> (string)

        

        

      value -> (boolean)

        

        

      

    requestModels -> (map)

      

      Specifies the  Model resources used for the request's content type. Request models are represented as a key/value map, with a content type as the key and a  Model name as the value.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    methodResponses -> (map)

      

      Represents available responses that can be sent to the caller. Method responses are represented as a key/value map, with an HTTP status code as the key and a  MethodResponse as the value. The status codes are available for the  Integration responses to map to.

      

      key -> (string)

        

        

      value -> (structure)

        

        Represents a method response. Amazon API Gateway sends back the status code to the caller as the HTTP status code. Parameters and models can be used to transform the response from the method's integration.

        

        statusCode -> (string)

          

          The method response's status code.

          

          

        responseParameters -> (map)

          

          Represents response parameters that can be sent back to the caller by Amazon API Gateway. Response parameters are represented as a key/value map, with a destination as the key and a boolean flag as the value, which is used to specify whether the parameter is required. A destination must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid, unique header name. Destinations specified here are available to the integration for mapping from integration response parameters.

          

          key -> (string)

            

            

          value -> (boolean)

            

            

          

        responseModels -> (map)

          

          Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

          

          key -> (string)

            

            

          value -> (string)

            

            

          

        

      

    methodIntegration -> (structure)

      

      The method's integration.

      

      type -> (string)

        

        Specifies the integration's type.

        

        

      httpMethod -> (string)

        

        Specifies the integration's HTTP method type.

        

        

      uri -> (string)

        

        Specifies the integration's Uniform Resource Identifier (URI). For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the `RFC-3986 specification`_ . For AWS integrations, the URI should be of the form ``arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`` . ``Region`` , ``subdomain`` and ``service`` are used to determine the right endpoint. For AWS services that use the ``Action=`` query string parameter, ``service_api`` should be a valid action for the desired service. For RESTful AWS service APIs, ``path`` is used to indicate that the remaining substring in the URI should be treated as the path to the resource, including the initial ``/`` .

        

        

      credentials -> (string)

        

        Specifies the credentials required for the integration, if any. For AWS integrations, three options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role's Amazon Resource Name (ARN). To require that the caller's identity be passed through from the request, specify the string ``arn:aws:iam::\*:user/\*`` . To use resource-based permissions on supported AWS services, specify null.

        

        

      requestParameters -> (map)

        

        Represents requests parameters that are sent with the backend request. Request parameters are represented as a key/value map, with a destination as the key and a source as the value. A source must match an existing method request parameter, or a static value. Static values must be enclosed with single quotes, and be pre-encoded based on their destination in the request. The destination must match the pattern ``integration.request.{location}.{name}`` , where ``location`` is either querystring, path, or header. ``name`` must be a valid, unique parameter name.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      requestTemplates -> (map)

        

        Specifies the integration's request templates.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      cacheNamespace -> (string)

        

        Specifies the integration's cache namespace.

        

        

      cacheKeyParameters -> (list)

        

        Specifies the integration's cache key parameters.

        

        (string)

          

          

        

      integrationResponses -> (map)

        

        Specifies the integration's responses.

        

        key -> (string)

          

          

        value -> (structure)

          

          Represents an integration response. The status code must map to an existing  MethodResponse , and parameters and templates can be used to transform the backend response.

          

          statusCode -> (string)

            

            Specifies the status code that is used to map the integration response to an existing  MethodResponse .

            

            

          selectionPattern -> (string)

            

            Specifies the regular expression (regex) pattern used to choose an integration response based on the response from the backend. If the backend is an AWS Lambda function, the AWS Lambda function error header is matched. For all other HTTP and AWS backends, the HTTP status code is matched.

            

            

          responseParameters -> (map)

            

            Represents response parameters that can be read from the backend response. Response parameters are represented as a key/value map, with a destination as the key and a source as the value. A destination must match an existing response parameter in the  MethodResponse . The source can be a header from the backend response, or a static value. Static values are specified using enclosing single quotes, and backend response headers can be read using the pattern ``integration.response.header.{name}`` .

            

            key -> (string)

              

              

            value -> (string)

              

              

            

          responseTemplates -> (map)

            

            Specifies the templates used to transform the integration response body. Response templates are represented as a key/value map, with a content-type as the key and a template as the value.

            

            key -> (string)

              

              

            value -> (string)

              

              

            

          

        

      

    

  



.. _RFC-3986 specification: https://www.ietf.org/rfc/rfc3986.txt
