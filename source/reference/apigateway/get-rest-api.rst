[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-rest-api:


************
get-rest-api
************



===========
Description
===========



Lists the  RestApi resource in the collection.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetRestApi>`_


========
Synopsis
========

::

    get-rest-api
  --rest-api-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The identifier of the  RestApi resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about an API**

Command::

  aws apigateway get-rest-api --rest-api-id 1234123412

Output::

  {
      "name": "myAPI", 
      "id": "o1y243m4f5", 
      "createdDate": 1453416433
  }


======
Output
======

id -> (string)

  

  The API's identifier. This identifier is unique across all of your APIs in Amazon API Gateway.

  

  

name -> (string)

  

  The API's name.

  

  

description -> (string)

  

  The API's description.

  

  

createdDate -> (timestamp)

  

  The timestamp when the API was created.

  

  

version -> (string)

  

  A version identifier for the API.

  

  

warnings -> (list)

  

  The warning messages reported when ``failonwarnings`` is turned on during API import.

  

  (string)

    

    

  

binaryMediaTypes -> (list)

  

  The list of binary media types supported by the  RestApi . By default, the  RestApi supports only UTF-8-encoded text payloads.

  

  (string)

    

    

  

