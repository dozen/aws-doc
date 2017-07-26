[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-api-key:


**************
create-api-key
**************



===========
Description
===========



========
Synopsis
========

::

    create-api-key
  [--name <value>]
  [--description <value>]
  [--enabled | --no-enabled]
  [--stage-keys <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the  ApiKey .

  

``--description`` (string)


  The description of the  ApiKey .

  

``--enabled`` | ``--no-enabled`` (boolean)


  Specifies whether the  ApiKey can be used by callers.

  

``--stage-keys`` (list)


  Specifies whether the  ApiKey can be used by callers.

  



Shorthand Syntax::

    restApiId=string,stageName=string ...




JSON Syntax::

  [
    {
      "restApiId": "string",
      "stageName": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

id -> (string)

  

  The identifier of the API Key.

  

  

name -> (string)

  

  The name of the API Key.

  

  

description -> (string)

  

  The description of the API Key.

  

  

enabled -> (boolean)

  

  Specifies whether the API Key can be used by callers.

  

  

stageKeys -> (list)

  

  A list of  Stage resources that are associated with the  ApiKey resource.

  

  (string)

    

    

  

createdDate -> (timestamp)

  

  The date when the API Key was created, in `ISO 8601 format`_ .

  

  

lastUpdatedDate -> (timestamp)

  

  When the API Key was last updated, in ISO 8601 format.

  

  



.. _ISO 8601 format: http://www.iso.org/iso/home/standards/iso8601.htm
