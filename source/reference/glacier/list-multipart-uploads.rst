[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier list-multipart-uploads:


**********************
list-multipart-uploads
**********************



===========
Description
===========



This operation lists in-progress multipart uploads for the specified vault. An in-progress multipart upload is a multipart upload that has been initiated by an  initiate-multipart-upload request, but has not yet been completed or aborted. The list returned in the List Multipart Upload response has no guaranteed order. 

 

The List Multipart Uploads operation supports pagination. By default, this operation returns up to 1,000 multipart uploads in the response. You should always check the response for a ``marker`` at which to continue the list; if there are no more items the ``marker`` is ``null`` . To return a list of multipart uploads that begins at a specific upload, set the ``marker`` request parameter to the value you obtained from a previous List Multipart Upload request. You can also limit the number of uploads returned in the response by specifying the ``limit`` parameter in the request.

 

Note the difference between this operation and listing parts ( list-parts ). The List Multipart Uploads operation lists all multipart uploads for a vault and does not require a multipart upload ID. The List Parts operation requires a multipart upload ID since parts are associated with a single upload.

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM) <http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html>`_ .

 

For conceptual information and the underlying REST API, see `Working with Archives in Amazon Glacier <http://docs.aws.amazon.com/amazonglacier/latest/dev/working-with-archives.html>`_ and `List Multipart Uploads <http://docs.aws.amazon.com/amazonglacier/latest/dev/api-multipart-list-uploads.html>`_ in the *Amazon Glacier Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/ListMultipartUploads>`_


``list-multipart-uploads`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``UploadsList``


========
Synopsis
========

::

    list-multipart-uploads
  --account-id <value>
  --vault-name <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single '``-`` ' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens ('-') in the ID. 

  

``--vault-name`` (string)


  The name of the vault.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (string)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (string)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command shows all of the in-progress multipart uploads for a vault named ``my-vault``::

  aws glacier list-multipart-uploads --account-id - --vault-name my-vault

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account. 

For more information on multipart uploads to Amazon Glacier using the AWS CLI, see `Using Amazon Glacier`_ in the *AWS CLI User Guide*.

.. _`Using Amazon Glacier`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-glacier.html

======
Output
======

UploadsList -> (list)

  

  A list of in-progress multipart uploads.

  

  (structure)

    

    A list of in-progress multipart uploads for a vault.

    

    MultipartUploadId -> (string)

      

      The ID of a multipart upload.

      

      

    VaultARN -> (string)

      

      The Amazon Resource Name (ARN) of the vault that contains the archive.

      

      

    ArchiveDescription -> (string)

      

      The description of the archive that was specified in the Initiate Multipart Upload request.

      

      

    PartSizeInBytes -> (long)

      

      The part size, in bytes, specified in the Initiate Multipart Upload request. This is the size of all the parts in the upload except the last part, which may be smaller than this size.

      

      

    CreationDate -> (string)

      

      The UTC time at which the multipart upload was initiated.

      

      

    

  

Marker -> (string)

  

  An opaque account-id that represents where to continue pagination of the results. You use the marker in a new List Multipart Uploads request to obtain more uploads in the list. If there are no more uploads, this value is ``null`` .

  

  

