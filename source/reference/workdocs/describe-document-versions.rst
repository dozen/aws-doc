[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs describe-document-versions:


**************************
describe-document-versions
**************************



===========
Description
===========



Retrieves the document versions for the specified document.

 

By default, only active versions are returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/DescribeDocumentVersions>`_


``describe-document-versions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DocumentVersions``


========
Synopsis
========

::

    describe-document-versions
  [--authentication-token <value>]
  --document-id <value>
  [--include <value>]
  [--fields <value>]
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

  

``--document-id`` (string)


  The ID of the document.

  

``--include`` (string)


  A comma-separated list of values. Specify "INITIALIZED" to include incomplete versions.

  

``--fields`` (string)


  Specify "SOURCE" to include initialized versions and a URL for the source document.

  

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

DocumentVersions -> (list)

  

  The document versions.

  

  (structure)

    

    Describes a version of a document.

    

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

        

        

      

    

  

Marker -> (string)

  

  The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

  

  

