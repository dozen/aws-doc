[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway import-documentation-parts:


**************************
import-documentation-parts
**************************



===========
Description
===========



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/ImportDocumentationParts>`_


========
Synopsis
========

::

    import-documentation-parts
  --rest-api-id <value>
  [--mode <value>]
  [--fail-on-warnings | --no-fail-on-warnings]
  --body <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  [Required] The string identifier of the associated  RestApi .

  

``--mode`` (string)


  A query parameter to indicate whether to overwrite (``OVERWRITE`` ) any existing  DocumentationParts definition or to merge (``MERGE`` ) the new definition into the existing one. The default value is ``MERGE`` .

  

  Possible values:

  
  *   ``merge``

  
  *   ``overwrite``

  

  

``--fail-on-warnings`` | ``--no-fail-on-warnings`` (boolean)


  A query parameter to specify whether to rollback the documentation importation (``true`` ) or not (``false`` ) when a warning is encountered. The default value is ``false`` .

  

``--body`` (blob)


  [Required] Raw byte array representing the to-be-imported documentation parts. To import from a Swagger file, this is a JSON object.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ids -> (list)

  

  A list of the returned documentation part identifiers.

  

  (string)

    

    

  

warnings -> (list)

  

  A list of warning messages reported during import of documentation parts.

  

  (string)

    

    

  

