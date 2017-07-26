[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs get-document-version:


********************
get-document-version
********************



===========
Description
===========



Retrieves version metadata for the specified document.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/GetDocumentVersion>`_


========
Synopsis
========

::

    get-document-version
  [--authentication-token <value>]
  --document-id <value>
  --version-id <value>
  [--fields <value>]
  [--include-custom-metadata | --no-include-custom-metadata]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--document-id`` (string)


  The ID of the document.

  

``--version-id`` (string)


  The version ID of the document.

  

``--fields`` (string)


  A comma-separated list of values. Specify "SOURCE" to include a URL for the source document.

  

``--include-custom-metadata`` | ``--no-include-custom-metadata`` (boolean)


  Set this to TRUE to include custom metadata in the response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Metadata -> (structure)

  

  The version metadata.

  

  Id -> (string)

    

    The ID of the version.

    

    

  Name -> (string)

    

    The name of the version.

    

    

  ContentType -> (string)

    

    The content type of the document.

    

    

  Size -> (long)

    

    The size of the document, in bytes.

    

    

  Signature -> (string)

    

    The signature of the document.

    

    

  Status -> (string)

    

    The status of the document.

    

    

  CreatedTimestamp -> (timestamp)

    

    The time stamp when the document was first uploaded.

    

    

  ModifiedTimestamp -> (timestamp)

    

    The time stamp when the document was last uploaded.

    

    

  ContentCreatedTimestamp -> (timestamp)

    

    The time stamp when the content of the document was originally created.

    

    

  ContentModifiedTimestamp -> (timestamp)

    

    The time stamp when the content of the document was modified.

    

    

  CreatorId -> (string)

    

    The ID of the creator.

    

    

  Thumbnail -> (map)

    

    The thumbnail of the document.

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  Source -> (map)

    

    The source of the document.

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  

CustomMetadata -> (map)

  

  The custom metadata on the document version.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

