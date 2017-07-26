[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier initiate-multipart-upload:


*************************
initiate-multipart-upload
*************************



===========
Description
===========



This operation initiates a multipart upload. Amazon Glacier creates a multipart upload resource and returns its ID in the response. The multipart upload ID is used in subsequent requests to upload parts of an archive (see  upload-multipart-part ).

 

When you initiate a multipart upload, you specify the part size in number of bytes. The part size must be a megabyte (1024 KB) multiplied by a power of 2-for example, 1048576 (1 MB), 2097152 (2 MB), 4194304 (4 MB), 8388608 (8 MB), and so on. The minimum allowable part size is 1 MB, and the maximum is 4 GB.

 

Every part you upload to this resource (see  upload-multipart-part ), except the last one, must have the same size. The last one can be the same size or smaller. For example, suppose you want to upload a 16.2 MB file. If you initiate the multipart upload with a part size of 4 MB, you will upload four parts of 4 MB each and one part of 0.2 MB. 

 

.. note::

  

  You don't need to know the size of the archive when you start a multipart upload because Amazon Glacier does not require you to specify the overall archive size.

  

 

After you complete the multipart upload, Amazon Glacier removes the multipart upload resource referenced by the ID. Amazon Glacier also removes the multipart upload resource if you cancel the multipart upload or it may be removed if there is no activity for a period of 24 hours.

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM)`_ .

 

For conceptual information and underlying REST API, go to `Uploading Large Archives in Parts (Multipart Upload)`_ and `Initiate Multipart Upload`_ in the *Amazon Glacier Developer Guide* .



========
Synopsis
========

::

    initiate-multipart-upload
  --account-id <value>
  --vault-name <value>
  [--archive-description <value>]
  [--part-size <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens (apos-apos) in the ID. 

  

``--vault-name`` (string)


  The name of the vault.

  

``--archive-description`` (string)


  The archive description that you are uploading in parts.

   

  The part size must be a megabyte (1024 KB) multiplied by a power of 2, for example 1048576 (1 MB), 2097152 (2 MB), 4194304 (4 MB), 8388608 (8 MB), and so on. The minimum allowable part size is 1 MB, and the maximum is 4 GB (4096 MB).

  

``--part-size`` (string)


  The size of each part except the last, in bytes. The last part can be smaller than this part size.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON part-size provided. The JSON part-size follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command initiates a multipart upload to a vault named ``my-vault`` with a part size of 1 MiB (1024 x 1024 bytes) per file::

  aws glacier initiate-multipart-upload --account-id - --part-size 1048576 --vault-name my-vault --archive-description "multipart upload test"

The archive description parameter is optional. Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.

This command outputs an upload ID when successful. Use the upload ID when uploading each part of your archive with ``aws glacier upload-multipart-part``. For more information on multipart uploads to Amazon Glacier using the AWS CLI, see `Using Amazon Glacier`_ in the *AWS CLI User Guide*.

.. _`Using Amazon Glacier`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-glacier.html

======
Output
======

location -> (string)

  

  The relative URI path of the multipart upload ID Amazon Glacier created. 

  

  

uploadId -> (string)

  

  The ID of the multipart upload. This value is also included as part of the location. 

  

  



.. _Access Control Using AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html
.. _Uploading Large Archives in Parts (Multipart Upload): http://docs.aws.amazon.com/amazonglacier/latest/dev/uploading-archive-mpu.html
.. _Initiate Multipart Upload: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-multipart-initiate-upload.html
