[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-request-validators:


**********************
get-request-validators
**********************



===========
Description
===========



Gets the  RequestValidators collection of a given  RestApi .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetRequestValidators>`_


========
Synopsis
========

::

    get-request-validators
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


  The current pagination position in the paged result set.

  

``--limit`` (integer)


  The maximum number of returned results per page.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

position -> (string)

  

  

items -> (list)

  

  The current page of elements from this collection.

  

  (structure)

    

    A set of validation rules for incoming  Method requests.

      

    In Swagger, a  RequestValidator of an API is defined by the `x-amazon-apigateway-request-validators.requestValidator <http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-swagger-extensions.html#api-gateway-swagger-extensions-request-validators.requestValidator.html>`_ object. It the referenced using the `x-amazon-apigateway-request-validator <http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-swagger-extensions.html#api-gateway-swagger-extensions-request-validator>`_ property.

      `Enable Basic Request Validation in API Gateway <http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-method-request-validation.html>`_ 

    id -> (string)

      

      The identifier of this  RequestValidator .

      

      

    name -> (string)

      

      The name of this  RequestValidator 

      

      

    validateRequestBody -> (boolean)

      

      A Boolean flag to indicate whether to validate a request body according to the configured  Model schema.

      

      

    validateRequestParameters -> (boolean)

      

      A Boolean flag to indicate whether to validate request parameters (``true`` ) or not (``false`` ).

      

      

    

  

