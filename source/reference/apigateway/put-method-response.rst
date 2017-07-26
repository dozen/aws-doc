[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway put-method-response:


*******************
put-method-response
*******************



===========
Description
===========



Adds a  MethodResponse to an existing  Method resource.



========
Synopsis
========

::

    put-method-response
  --rest-api-id <value>
  --resource-id <value>
  --http-method <value>
  --status-code <value>
  [--response-parameters <value>]
  [--response-models <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The  RestApi identifier for the  Method resource.

  

``--resource-id`` (string)


  The  Resource identifier for the  Method resource.

  

``--http-method`` (string)


  The HTTP verb that identifies the  Method resource.

  

``--status-code`` (string)


  The method response's status code.

  

``--response-parameters`` (map)


  Represents response parameters that can be sent back to the caller by Amazon API Gateway. Response parameters are represented as a key/value map, with a destination as the key and a Boolean flag as the value. The Boolean flag is used to specify whether the parameter is required. A destination must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid, unique header name. Destinations specified here are available to the integration for mapping from integration response parameters.

  



Shorthand Syntax::

    KeyName1=boolean,KeyName2=boolean




JSON Syntax::

  {"string": true|false
    ...}



``--response-models`` (map)


  Specifies the  Model resources used for the response's content type. Response models are represented as a key/value map, with a content type as the key and a  Model name as the value.

  



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

    

    

  

