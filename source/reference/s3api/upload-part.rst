[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api upload-part:


***********
upload-part
***********



===========
Description
===========



Uploads a part in a multipart upload.



**Note:** After you initiate multipart upload and upload one or more parts, you must either complete or abort multipart upload in order to stop getting charged for storage of the uploaded parts. Only after you either complete or abort multipart upload, Amazon S3 frees up the parts storage and stops charging you for the parts storage.



========
Synopsis
========

::

    upload-part
  [--body <value>]
  --bucket <value>
  [--content-length <value>]
  [--content-md5 <value>]
  --key <value>
  --part-number <value>
  --upload-id <value>
  [--sse-customer-algorithm <value>]
  [--sse-customer-key <value>]
  [--sse-customer-key-md5 <value>]
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--body`` (blob)


``--bucket`` (string)


``--content-length`` (integer)
Size of the body in bytes. This parameter is useful when the size of the body cannot be determined automatically.

``--content-md5`` (string)


``--key`` (string)


``--part-number`` (integer)
Part number of part being uploaded. This is a positive integer between 1 and 10,000.

``--upload-id`` (string)
Upload ID identifying the multipart upload whose part is being uploaded.

``--sse-customer-algorithm`` (string)
Specifies the algorithm to use to when encrypting the object (e.g., AES256).

``--sse-customer-key`` (string)
Specifies the customer-provided encryption key for Amazon S3 to use in encrypting data. This value is used to store the object and then it is discarded; Amazon does not store the encryption key. The key must be appropriate for use with the algorithm specified in the x-amz-server-side​-encryption​-customer-algorithm header. This must be the same encryption key specified in the initiate multipart upload request.

``--sse-customer-key-md5`` (string)
Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure the encryption key was transmitted without error.

``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the request. Bucket owners need not specify this parameter in their requests. Documentation on downloading objects from requester pays buckets can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectsinRequesterPaysBuckets.html

  Possible values:

  
  *   ``requester``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command uploads the first part in a multipart upload initiated with the ``create-multipart-upload`` command::

  aws s3api upload-part --bucket my-bucket --key 'multipart/01' --part-number 1 --body part01 --upload-id  "dfRtDYU0WWCCcH43C3WFbkRONycyCpTJJvxu2i5GYkZljF.Yxwh6XG7WfS2vC4to6HiV6Yjlx.cph0gtNBtJ8P3URCSbB7rjxI5iEwVDmgaXZOGgkk5nVTW16HOQ5l0R"

The ``body`` option takes the name or path of a local file for upload (do not use the file:// prefix). The minimum part size is 5 MB. Upload ID is returned by ``create-multipart-upload`` and can also be retrieved with ``list-multipart-uploads``. Bucket and key are specified when you create the multipart upload.

Output::

  {
      "ETag": "\"e868e0f4719e394144ef36531ee6824c\""
  }

Save the ETag value of each part for later. They are required to complete the multipart upload.

======
Output
======

ServerSideEncryption -> (string)

  The Server-side encryption algorithm used when storing this object in S3 (e.g., AES256, aws:kms).

  

ETag -> (string)

  Entity tag for the uploaded object.

  

SSECustomerAlgorithm -> (string)

  If server-side encryption with a customer-provided encryption key was requested, the response will include this header confirming the encryption algorithm used.

  

SSECustomerKeyMD5 -> (string)

  If server-side encryption with a customer-provided encryption key was requested, the response will include this header to provide round trip message integrity verification of the customer-provided encryption key.

  

SSEKMSKeyId -> (string)

  If present, specifies the ID of the AWS Key Management Service (KMS) master encryption key that was used for the object.

  

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

