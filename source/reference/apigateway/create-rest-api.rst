[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-rest-api:


***************
create-rest-api
***************



===========
Description
===========



Creates a new  RestApi resource.



========
Synopsis
========

::

    create-rest-api
  --name <value>
  [--description <value>]
  [--clone-from <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the  RestApi .

  

``--description`` (string)


  The description of the  RestApi .

  

``--clone-from`` (string)


  The Id of the  RestApi that you want to clone from.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  The date when the API was created, in `ISO 8601 format`_ .

  

  



.. _ISO 8601 format: http://www.iso.org/iso/home/standards/iso8601.htm
