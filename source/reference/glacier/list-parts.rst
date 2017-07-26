[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier list-parts:


**********
list-parts
**********



===========
Description
===========



This operation lists the parts of an archive that have been uploaded in a specific multipart upload. You can make this request at any time during an in-progress multipart upload before you complete the upload (see  complete-multipart-upload . List Parts returns an error for completed uploads. The list returned in the List Parts response is sorted by part range. 

 

The List Parts operation supports pagination. By default, this operation returns up to 1,000 uploaded parts in the response. You should always check the response for a ``marker`` at which to continue the list; if there are no more items the ``marker`` is ``null`` . To return a list of parts that begins at a specific part, set the ``marker`` request parameter to the value you obtained from a previous List Parts request. You can also limit the number of parts returned in the response by specifying the ``limit`` parameter in the request. 

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM) <http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html>`_ .

 

For conceptual information and the underlying REST API, see `Working with Archives in Amazon Glacier <http://docs.aws.amazon.com/amazonglacier/latest/dev/working-with-archives.html>`_ and `List Parts <http://docs.aws.amazon.com/amazonglacier/latest/dev/api-multipart-list-parts.html>`_ in the *Amazon Glacier Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/ListParts>`_


``list-parts`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Parts``


========
Synopsis
========

::

    list-parts
  --account-id <value>
  --vault-name <value>
  --upload-id <value>
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

  

``--upload-id`` (string)


  The upload ID of the multipart upload.

  

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

The following command lists the uploaded parts for a multipart upload to a vault named ``my-vault``::

  aws glacier list-parts --account-id - --vault-name my-vault --upload-id "SYZi7qnL-YGqGwAm8Kn3BLP2ElNCvnB-5961R09CSaPmPwkYGHOqeN_nX3-Vhnd2yF0KfB5FkmbnBU9GubbdrCs8ut-D"

Output::

  {
      "MultipartUploadId": "SYZi7qnL-YGqGwAm8Kn3BLP2ElNCvnB-5961R09CSaPmPwkYGHOqeN_nX3-Vhnd2yF0KfB5FkmbnBU9GubbdrCs8ut-D",
      "Parts": [
          {
              "RangeInBytes": "0-1048575",
              "SHA256TreeHash": "e1f2a7cd6e047350f69b9f8cfa60fa606fe2f02802097a9a026360a7edc1f553"
          },
          {
              "RangeInBytes": "1048576-2097151",
              "SHA256TreeHash": "43cf3061fb95796aed99a11a6aa3cd8f839eed15e655ab0a597126210636aee6"
          }
      ],
      "VaultARN": "arn:aws:glacier:us-west-2:0123456789012:vaults/my-vault",
      "CreationDate": "2015-07-18T00:05:23.830Z",
      "PartSizeInBytes": 1048576
  }

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.

For more information on multipart uploads to Amazon Glacier using the AWS CLI, see `Using Amazon Glacier`_ in the *AWS CLI User Guide*.

.. _`Using Amazon Glacier`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-glacier.html

======
Output
======

MultipartUploadId -> (string)

  

  The ID of the upload to which the parts are associated.

  

  

VaultARN -> (string)

  

  The Amazon Resource Name (ARN) of the vault to which the multipart upload was initiated.

  

  

ArchiveDescription -> (string)

  

  The description of the archive that was specified in the Initiate Multipart Upload request.

  

  

PartSizeInBytes -> (long)

  

  The part size in bytes. This is the same value that you specified in the Initiate Multipart Upload request.

  

  

CreationDate -> (string)

  

  The UTC time at which the multipart upload was initiated.

  

  

Parts -> (list)

  

  A list of the part sizes of the multipart upload. Each object in the array contains a ``RangeBytes`` and ``sha256-tree-hash`` name/value pair.

  

  (structure)

    

    A list of the part sizes of the multipart upload.

    

    RangeInBytes -> (string)

      

      The byte range of a part, inclusive of the upper value of the range.

      

      

    SHA256TreeHash -> (string)

      

      The SHA256 tree hash value that Amazon Glacier calculated for the part. This field is never ``null`` .

      

      

    

  

Marker -> (string)

  

  An opaque account-id that represents where to continue pagination of the results. You use the marker in a new List Parts request to obtain more jobs in the list. If there are no more parts, this value is ``null`` .

  

  

