[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs initiate-document-version-upload:


********************************
initiate-document-version-upload
********************************



===========
Description
===========



Creates a new document object and version object.

 

The client specifies the parent folder ID and name of the document to upload. The ID is optionally specified when creating a new version of an existing document. This is the first step to upload a document. Next, upload the document to the URL returned from the call, and then call  update-document-version .

 

To cancel the document upload, call  abort-document-version-upload .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/InitiateDocumentVersionUpload>`_


========
Synopsis
========

::

    initiate-document-version-upload
  [--authentication-token <value>]
  [--id <value>]
  [--name <value>]
  [--content-created-timestamp <value>]
  [--content-modified-timestamp <value>]
  [--content-type <value>]
  [--document-size-in-bytes <value>]
  --parent-folder-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--id`` (string)


  The ID of the document.

  

``--name`` (string)


  The name of the document.

  

``--content-created-timestamp`` (timestamp)


  The time stamp when the content of the document was originally created.

  

``--content-modified-timestamp`` (timestamp)


  The time stamp when the content of the document was modified.

  

``--content-type`` (string)


  The content type of the document.

  

``--document-size-in-bytes`` (long)


  The size of the document, in bytes.

  

``--parent-folder-id`` (string)


  The ID of the parent folder.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Metadata -> (structure)

  

  The document metadata.

  

  Id -> (string)

    

    The ID of the document.

    

    

  CreatorId -> (string)

    

    The ID of the creator.

    

    

  ParentFolderId -> (string)

    

    The ID of the parent folder.

    

    

  CreatedTimestamp -> (timestamp)

    

    The time when the document was created.

    

    

  ModifiedTimestamp -> (timestamp)

    

    The time when the document was updated.

    

    

  LatestVersionMetadata -> (structure)

    

    The latest version of the document.

    

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

        

        

      

    

  ResourceState -> (string)

    

    The resource state.

    

    

  Labels -> (list)

    

    List of labels on the document.

    

    (string)

      

      

    

  

UploadMetadata -> (structure)

  

  The upload metadata.

  

  UploadUrl -> (string)

    

    The URL of the upload.

    

    

  SignedHeaders -> (map)

    

    The signed headers.

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  

