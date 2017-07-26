[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-api-key:


***********
get-api-key
***********



===========
Description
===========



Gets information about the current  ApiKey resource.



========
Synopsis
========

::

    get-api-key
  --api-key <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--api-key`` (string)


  The identifier of the  ApiKey resource.

  

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
