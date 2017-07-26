[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-model:


************
create-model
************



===========
Description
===========



Adds a new  Model resource to an existing  RestApi resource.



========
Synopsis
========

::

    create-model
  --rest-api-id <value>
  --name <value>
  [--description <value>]
  [--schema <value>]
  --content-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The  RestApi identifier under which the  Model will be created.

  

``--name`` (string)


  The name of the model.

  

``--description`` (string)


  The description of the model.

  

``--schema`` (string)


  The schema for the model. For ``application/json`` models, this should be `JSON-schema draft v4`_ model.

  

``--content-type`` (string)


  The content-type for the model.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

id -> (string)

  

  The identifier for the model resource.

  

  

name -> (string)

  

  The name of the model.

  

  

description -> (string)

  

  The description of the model.

  

  

schema -> (string)

  

  The schema for the model. For ``application/json`` models, this should be `JSON-schema draft v4`_ model.

  

  

contentType -> (string)

  

  The content-type for the model.

  

  



.. _JSON-schema draft v4: http://json-schema.org/documentation.html
