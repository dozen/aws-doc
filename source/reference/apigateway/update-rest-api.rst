[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-rest-api:


***************
update-rest-api
***************



===========
Description
===========



Changes information about the specified API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/UpdateRestApi>`_


========
Synopsis
========

::

    update-rest-api
  --rest-api-id <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--patch-operations`` (list)


  A list of update operations to be applied to the specified resource and in the order specified in this list.

  



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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change the name of an API**

Command::

  aws apigateway update-rest-api --rest-api-id 1234123412 --patch-operations op=replace,path=/name,value='New Name'

**To change the description of an API**

Command::

  aws apigateway update-rest-api --rest-api-id 1234123412 --patch-operations op=replace,path=/description,value='New Description'


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

    

    

  

