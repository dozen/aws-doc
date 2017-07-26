[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway import-api-keys:


***************
import-api-keys
***************



===========
Description
===========



Import API keys from an external source, such as a CSV-formatted file.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/ImportApiKeys>`_


========
Synopsis
========

::

    import-api-keys
  --body <value>
  --format <value>
  [--fail-on-warnings | --no-fail-on-warnings]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--body`` (blob)


  The payload of the POST request to import API keys. For the payload format, see `API Key File Format <http://docs.aws.amazon.com/apigateway/latest/developerguide/api-key-file-format.html>`_ .

  

``--format`` (string)


  A query parameter to specify the input format to imported API keys. Currently, only the ``csv`` format is supported.

  

  Possible values:

  
  *   ``csv``

  

  

``--fail-on-warnings`` | ``--no-fail-on-warnings`` (boolean)


  A query parameter to indicate whether to rollback  ApiKey importation (``true`` ) or not (``false`` ) when error is encountered.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ids -> (list)

  

  A list of all the  ApiKey identifiers.

  

  (string)

    

    

  

warnings -> (list)

  

  A list of warning messages.

  

  (string)

    

    

  

