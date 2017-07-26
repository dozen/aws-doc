[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-rest-api:


***************
create-rest-api
***************



===========
Description
===========



Creates a new  RestApi resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/CreateRestApi>`_


========
Synopsis
========

::

    create-rest-api
  --name <value>
  [--description <value>]
  [--clone-from <value>]
  [--binary-media-types <value>]
  [--api-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the  RestApi .

  

``--description`` (string)


  The description of the  RestApi .

  

``--clone-from`` (string)


  The ID of the  RestApi that you want to clone from.

  

``--binary-media-types`` (list)


  The list of binary media types supported by the  RestApi . By default, the  RestApi supports only UTF-8-encoded text payloads.

  



Syntax::

  "string" "string" ...



``--api-version`` (string)


  A version identifier for the API.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an API**

Command::

  aws apigateway create-rest-api --name 'My First API' --description 'This is my first API'

**To create a duplicate API from an existing API**

Command::

  aws apigateway create-rest-api --name 'Copy of My First API' --description 'This is a copy of my first API' --clone-from 1234123412


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

    

    

  

