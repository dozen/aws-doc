[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier upload-multipart-part:


*********************
upload-multipart-part
*********************



===========
Description
===========



This operation uploads a part of an archive. You can upload archive parts in any order. You can also upload them in parallel. You can upload up to 10,000 parts for a multipart upload.

 

Amazon Glacier rejects your upload part request if any of the following conditions is true:

 

 
* **SHA256 tree hash does not match** To ensure that part data is not corrupted in transmission, you compute a SHA256 tree hash of the part and include it in your request. Upon receiving the part data, Amazon Glacier also computes a SHA256 tree hash. If these hash values don't match, the operation fails. For information about computing a SHA256 tree hash, see `Computing Checksums <http://docs.aws.amazon.com/amazonglacier/latest/dev/checksum-calculations.html>`_ . 
 
* **Part size does not match** The size of each part except the last must match the size specified in the corresponding  initiate-multipart-upload request. The size of the last part must be the same size as, or smaller than, the specified size. 

.. note::

   If you upload a part whose size is smaller than the part size you specified in your initiate multipart upload request and that part is not the last part, then the upload part request will succeed. However, the subsequent Complete Multipart Upload request will fail. 

 
 
* **Range does not align** The byte range value in the request does not align with the part size specified in the corresponding initiate request. For example, if you specify a part size of 4194304 bytes (4 MB), then 0 to 4194303 bytes (4 MB - 1) and 4194304 (4 MB) to 8388607 (8 MB - 1) are valid part ranges. However, if you set a range value of 2 MB to 6 MB, the range does not align with the part size and the upload will fail.  
 

 

This operation is idempotent. If you upload the same part multiple times, the data included in the most recent request overwrites the previously uploaded data.

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM) <http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html>`_ .

 

For conceptual information and underlying REST API, see `Uploading Large Archives in Parts (Multipart Upload) <http://docs.aws.amazon.com/amazonglacier/latest/dev/uploading-archive-mpu.html>`_ and `Upload Part <http://docs.aws.amazon.com/amazonglacier/latest/dev/api-upload-part.html>`_ in the *Amazon Glacier Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/UploadMultipartPart>`_


========
Synopsis
========

::

    upload-multipart-part
  --account-id <value>
  --vault-name <value>
  --upload-id <value>
  [--checksum <value>]
  [--range <value>]
  [--body <value>]
  [--cli-input-json <value>]
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

  

``--checksum`` (string)


  The SHA256 tree hash of the data being uploaded.

  

``--range`` (string)


  Identifies the range of bytes in the assembled archive that will be uploaded in this part. Amazon Glacier uses this information to assemble the archive in the proper sequence. The format of this header follows RFC 2616. An example header is Content-Range:bytes 0-4194303/*.

  

``--body`` (blob)


  The data to upload.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command uploads the first 1 MiB (1024 x 1024 bytes) part of an archive::

  aws glacier upload-multipart-part --body part1 --range 'bytes 0-1048575/*' --account-id - --vault-name my-vault --upload-id 19gaRezEXAMPLES6Ry5YYdqthHOC_kGRCT03L9yetr220UmPtBYKk-OssZtLqyFu7sY1_lR7vgFuJV6NtcV5zpsJ

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account. 

The body parameter takes a path to a part file on the local filesystem. The range parameter takes an HTTP content range indicating the bytes that the part occupies in the completed archive. The upload ID is returned by the ``aws glacier initiate-multipart-upload`` command and can also be obtained by using ``aws glacier list-multipart-uploads``.

For more information on multipart uploads to Amazon Glacier using the AWS CLI, see `Using Amazon Glacier`_ in the *AWS CLI User Guide*.

.. _`Using Amazon Glacier`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-glacier.html

======
Output
======

checksum -> (string)

  

  The SHA256 tree hash that Amazon Glacier computed for the uploaded part.

  

  

