[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-request-validator:


************************
update-request-validator
************************



===========
Description
===========



Updates a  RequestValidator of a given  RestApi .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/UpdateRequestValidator>`_


========
Synopsis
========

::

    update-request-validator
  --rest-api-id <value>
  --request-validator-id <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--request-validator-id`` (string)


  [Required] The identifier of  RequestValidator to be updated.

  

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



======
Output
======

id -> (string)

  

  The identifier of this  RequestValidator .

  

  

name -> (string)

  

  The name of this  RequestValidator 

  

  

validateRequestBody -> (boolean)

  

  A Boolean flag to indicate whether to validate a request body according to the configured  Model schema.

  

  

validateRequestParameters -> (boolean)

  

  A Boolean flag to indicate whether to validate request parameters (``true`` ) or not (``false`` ).

  

  

