[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-request-validator:


************************
create-request-validator
************************



===========
Description
===========



Creates a  ReqeustValidator of a given  RestApi .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/CreateRequestValidator>`_


========
Synopsis
========

::

    create-request-validator
  --rest-api-id <value>
  [--name <value>]
  [--validate-request-body | --no-validate-request-body]
  [--validate-request-parameters | --no-validate-request-parameters]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--name`` (string)


  The name of the to-be-created  RequestValidator .

  

``--validate-request-body`` | ``--no-validate-request-body`` (boolean)


  A validate-request-body flag to indicate whether to validate request body according to the configured model schema for the method (``true`` ) or not (``false`` ).

  

``--validate-request-parameters`` | ``--no-validate-request-parameters`` (boolean)


  A validate-request-body flag to indicate whether to validate request parameters, ``true`` , or not ``false`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

id -> (string)

  

  The identifier of this  RequestValidator .

  

  

name -> (string)

  

  The name of this  RequestValidator 

  

  

validateRequestBody -> (boolean)

  

  A validate-request-body flag to indicate whether to validate a request body according to the configured  Model schema.

  

  

validateRequestParameters -> (boolean)

  

  A validate-request-body flag to indicate whether to validate request parameters (``true`` ) or not (``false`` ).

  

  

