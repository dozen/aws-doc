[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api upload-part-copy:


****************
upload-part-copy
****************



===========
Description
===========

Uploads a part by copying data from an existing object as data source.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/UploadPartCopy>`_


========
Synopsis
========

::

    upload-part-copy
  --bucket <value>
  --copy-source <value>
  [--copy-source-if-match <value>]
  [--copy-source-if-modified-since <value>]
  [--copy-source-if-none-match <value>]
  [--copy-source-if-unmodified-since <value>]
  [--copy-source-range <value>]
  --key <value>
  --part-number <value>
  --upload-id <value>
  [--sse-customer-algorithm <value>]
  [--sse-customer-key <value>]
  [--sse-customer-key-md5 <value>]
  [--copy-source-sse-customer-algorithm <value>]
  [--copy-source-sse-customer-key <value>]
  [--copy-source-sse-customer-key-md5 <value>]
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--copy-source`` (string)
The name of the source bucket and key name of the source object, separated by a slash (/). Must be URL-encoded.

``--copy-source-if-match`` (string)
Copies the object if its entity tag (ETag) matches the specified tag.

``--copy-source-if-modified-since`` (timestamp)
Copies the object if it has been modified since the specified time.

``--copy-source-if-none-match`` (string)
Copies the object if its entity tag (ETag) is different than the specified ETag.

``--copy-source-if-unmodified-since`` (timestamp)
Copies the object if it hasn't been modified since the specified time.

``--copy-source-range`` (string)
The range of bytes to copy from the source object. The range value must use the form bytes=first-last, where the first and last are the zero-based byte offsets to copy. For example, bytes=0-9 indicates that you want to copy the first ten bytes of the source. You can copy a range only if the source object is greater than 5 GB.

``--key`` (string)


``--part-number`` (integer)
Part number of part being copied. This is a positive integer between 1 and 10,000.

``--upload-id`` (string)
Upload ID identifying the multipart upload whose part is being copied.

``--sse-customer-algorithm`` (string)
Specifies the algorithm to use to when encrypting the object (e.g., AES256).

``--sse-customer-key`` (string)
Specifies the customer-provided encryption key for Amazon S3 to use in encrypting data. This value is used to store the object and then it is discarded; Amazon does not store the encryption key. The key must be appropriate for use with the algorithm specified in the x-amz-server-side​-encryption​-customer-algorithm header. This must be the same encryption key specified in the initiate multipart upload request.

``--sse-customer-key-md5`` (string)
Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure the encryption key was transmitted without error.

``--copy-source-sse-customer-algorithm`` (string)
Specifies the algorithm to use when decrypting the source object (e.g., AES256).

``--copy-source-sse-customer-key`` (string)
Specifies the customer-provided encryption key for Amazon S3 to use to decrypt the source object. The encryption key provided in this header must be one that was used when the source object was created.

``--copy-source-sse-customer-key-md5`` (string)
Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure the encryption key was transmitted without error.

``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the request. Bucket owners need not specify this parameter in their requests. Documentation on downloading objects from requester pays buckets can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectsinRequesterPaysBuckets.html

  Possible values:

  
  *   ``requester``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CopySourceVersionId -> (string)

  The version of the source object that was copied, if you have enabled versioning on the source bucket.

  

CopyPartResult -> (structure)

  

  ETag -> (string)

    Entity tag of the object.

    

  LastModified -> (timestamp)

    Date and time at which the object was uploaded.

    

  

ServerSideEncryption -> (string)

  The Server-side encryption algorithm used when storing this object in S3 (e.g., AES256, aws:kms).

  

SSECustomerAlgorithm -> (string)

  If server-side encryption with a customer-provided encryption key was requested, the response will include this header confirming the encryption algorithm used.

  

SSECustomerKeyMD5 -> (string)

  If server-side encryption with a customer-provided encryption key was requested, the response will include this header to provide round trip message integrity verification of the customer-provided encryption key.

  

SSEKMSKeyId -> (string)

  If present, specifies the ID of the AWS Key Management Service (KMS) master encryption key that was used for the object.

  

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

