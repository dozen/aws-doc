[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs describe-folder-contents:


************************
describe-folder-contents
************************



===========
Description
===========



Describes the contents of the specified folder, including its documents and subfolders.

 

By default, Amazon WorkDocs returns the first 100 active document and folder metadata items. If there are more results, the response includes a marker that you can use to request the next set of results. You can also request initialized documents.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/DescribeFolderContents>`_


``describe-folder-contents`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Folders``, ``Documents``


========
Synopsis
========

::

    describe-folder-contents
  [--authentication-token <value>]
  --folder-id <value>
  [--sort <value>]
  [--order <value>]
  [--type <value>]
  [--include <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--folder-id`` (string)


  The ID of the folder.

  

``--sort`` (string)


  The sorting criteria.

  

  Possible values:

  
  *   ``DATE``

  
  *   ``NAME``

  

  

``--order`` (string)


  The order for the contents of the folder.

  

  Possible values:

  
  *   ``ASCENDING``

  
  *   ``DESCENDING``

  

  

``--type`` (string)


  The type of items.

  

  Possible values:

  
  *   ``ALL``

  
  *   ``DOCUMENT``

  
  *   ``FOLDER``

  

  

``--include`` (string)


  The contents to include. Specify "INITIALIZED" to include initialized documents.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Folders -> (list)

  

  The subfolders in the specified folder.

  

  (structure)

    

    Describes a folder.

    

    Id -> (string)

      

      The ID of the folder.

      

      

    Name -> (string)

      

      The name of the folder.

      

      

    CreatorId -> (string)

      

      The ID of the creator.

      

      

    ParentFolderId -> (string)

      

      The ID of the parent folder.

      

      

    CreatedTimestamp -> (timestamp)

      

      The time when the folder was created.

      

      

    ModifiedTimestamp -> (timestamp)

      

      The time when the folder was updated.

      

      

    ResourceState -> (string)

      

      The resource state of the folder.

      

      

    Signature -> (string)

      

      The unique identifier created from the subfolders and documents of the folder.

      

      

    Labels -> (list)

      

      List of labels on the folder.

      

      (string)

        

        

      

    Size -> (long)

      

      The size of the folder metadata.

      

      

    LatestVersionSize -> (long)

      

      The size of the latest version of the folder metadata.

      

      

    

  

Documents -> (list)

  

  The documents in the specified folder.

  

  (structure)

    

    Describes the document.

    

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

        

        

      

    

  

Marker -> (string)

  

  The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

  

  

