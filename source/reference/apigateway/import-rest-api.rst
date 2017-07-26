[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway import-rest-api:


***************
import-rest-api
***************



===========
Description
===========



A feature of the Amazon API Gateway control service for creating a new API from an external API definition file.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/ImportRestApi>`_


========
Synopsis
========

::

    import-rest-api
  [--fail-on-warnings | --no-fail-on-warnings]
  [--parameters <value>]
  --body <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fail-on-warnings`` | ``--no-fail-on-warnings`` (boolean)


  A query parameter to indicate whether to rollback the API creation (``true`` ) or not (``false`` ) when a warning is encountered. The default value is ``false`` .

  

``--parameters`` (map)


  Custom header parameters as part of the request. For example, to exclude  DocumentationParts from an imported API, set ``ignore=documentation`` as a ``parameters`` value, as in the AWS CLI command of ``aws apigateway import-rest-api --parameters ignore=documentation --body 'file:///path/to/imported-api-body.json`` .

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--body`` (blob)


  The POST request body containing external API definitions. Currently, only Swagger definition JSON files are supported. The maximum size of the API definition file is 2MB.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To import a Swagger template and create an API**

Command::

  aws apigateway import-rest-api --body 'file:///path/to/API_Swagger_template.json'


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

    

    

  

