[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-integration-response:


***************************
update-integration-response
***************************



===========
Description
===========



Represents an update integration response.



========
Synopsis
========

::

    update-integration-response
  --rest-api-id <value>
  --resource-id <value>
  --http-method <value>
  --status-code <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  Specifies an update integration response request's API identifier.

  

``--resource-id`` (string)


  Specifies an update integration response request's resource identifier.

  

``--http-method`` (string)


  Specifies an update integration response request's HTTP method.

  

``--status-code`` (string)


  Specifies an update integration response request's status code.

  

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

    

    

  

