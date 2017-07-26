[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-method-response:


*******************
get-method-response
*******************



===========
Description
===========



Describes a  MethodResponse resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetMethodResponse>`_


========
Synopsis
========

::

    get-method-response
  --rest-api-id <value>
  --resource-id <value>
  --http-method <value>
  --status-code <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--resource-id`` (string)


  The  Resource identifier for the  MethodResponse resource.

  

``--http-method`` (string)


  The HTTP verb of the  Method resource.

  

``--status-code`` (string)


  The status code for the  MethodResponse resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the method response resource configuration for a HTTP method defined under a REST API's resource**

Command::

  aws apigateway get-method-response --rest-api-id 1234123412 --resource-id y9h6rt --http-method GET --status-code 200

Output::

  {
      "responseModels": {
          "application/json": "Empty"
      }, 
      "statusCode": "200"
  }



======
Output
======

statusCode -> (string)

  

  The method response's status code.

  

  

responseParameters -> (map)

  

  A key-value map specifying required or optional response parameters that Amazon API Gateway can send back to the caller. A key defines a method response header and the value specifies whether the associated method response header is required or not. The expression of the key must match the pattern ``method.response.header.{name}`` , where ``name`` is a valid and unique header name. Amazon API Gateway passes certain integration response data to the method response headers specified here according to the mapping you prescribe in the API's  IntegrationResponse . The integration response data that can be mapped include an integration response header expressed in ``integration.response.header.{name}`` , a static value enclosed within a pair of single quotes (e.g., ``'application/json'`` ), or a JSON expression from the back-end response payload in the form of ``integration.response.body.{JSON-expression}`` , where ``JSON-expression`` is a valid JSON expression without the ``$`` prefix.)

  

  key -> (string)

    

    

  value -> (boolean)

    

    

  

responseModels -> (map)

  

  Specifies the  Model resources used for the response's content-type. Response models are represented as a key/value map, with a content-type as the key and a  Model name as the value.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

