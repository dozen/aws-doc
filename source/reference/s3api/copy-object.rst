[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api copy-object:


***********
copy-object
***********



===========
Description
===========

Creates a copy of an object that is already stored in Amazon S3.

========
Synopsis
========

::

    copy-object
  [--acl <value>]
  --bucket <value>
  [--cache-control <value>]
  [--content-disposition <value>]
  [--content-encoding <value>]
  [--content-language <value>]
  [--content-type <value>]
  --copy-source <value>
  [--copy-source-if-match <value>]
  [--copy-source-if-modified-since <value>]
  [--copy-source-if-none-match <value>]
  [--copy-source-if-unmodified-since <value>]
  [--expires <value>]
  [--grant-full-control <value>]
  [--grant-read <value>]
  [--grant-read-acp <value>]
  [--grant-write-acp <value>]
  --key <value>
  [--metadata <value>]
  [--metadata-directive <value>]
  [--server-side-encryption <value>]
  [--storage-class <value>]
  [--website-redirect-location <value>]
  [--sse-customer-algorithm <value>]
  [--sse-customer-key <value>]
  [--sse-customer-key-md5 <value>]
  [--ssekms-key-id <value>]
  [--copy-source-sse-customer-algorithm <value>]
  [--copy-source-sse-customer-key <value>]
  [--copy-source-sse-customer-key-md5 <value>]
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--acl`` (string)
The canned ACL to apply to the object.

  Possible values:

  
  *   ``private``

  
  *   ``public-read``

  
  *   ``public-read-write``

  
  *   ``authenticated-read``

  
  *   ``aws-exec-read``

  
  *   ``bucket-owner-read``

  
  *   ``bucket-owner-full-control``

  

  

``--bucket`` (string)


``--cache-control`` (string)
Specifies caching behavior along the request/reply chain.

``--content-disposition`` (string)
Specifies presentational information for the object.

``--content-encoding`` (string)
Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field.

``--content-language`` (string)
The language the content is in.

``--content-type`` (string)
A standard MIME type describing the format of the object data.

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

``--expires`` (timestamp)
The date and time at which the object is no longer cacheable.

``--grant-full-control`` (string)
Gives the grantee READ, READ_ACP, and WRITE_ACP permissions on the object.

``--grant-read`` (string)
Allows grantee to read the object data and its metadata.

``--grant-read-acp`` (string)
Allows grantee to read the object ACL.

``--grant-write-acp`` (string)
Allows grantee to write the ACL for the applicable object.

``--key`` (string)


``--metadata`` (map)
A map of metadata to store with the object in S3.



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--metadata-directive`` (string)
Specifies whether the metadata is copied from the source object or replaced with metadata provided in the request.

  Possible values:

  
  *   ``COPY``

  
  *   ``REPLACE``

  

  

``--server-side-encryption`` (string)
The Server-side encryption algorithm used when storing this object in S3 (e.g., AES256, aws:kms).

  Possible values:

  
  *   ``AES256``

  
  *   ``aws:kms``

  

  

``--storage-class`` (string)
The type of storage to use for the object. Defaults to 'STANDARD'.

  Possible values:

  
  *   ``STANDARD``

  
  *   ``REDUCED_REDUNDANCY``

  
  *   ``STANDARD_IA``

  

  

``--website-redirect-location`` (string)
If the bucket is configured as a website, redirects requests for this object to another object in the same bucket or to an external URL. Amazon S3 stores the value of this header in the object metadata.

``--sse-customer-algorithm`` (string)
Specifies the algorithm to use to when encrypting the object (e.g., AES256).

``--sse-customer-key`` (string)
Specifies the customer-provided encryption key for Amazon S3 to use in encrypting data. This value is used to store the object and then it is discarded; Amazon does not store the encryption key. The key must be appropriate for use with the algorithm specified in the x-amz-server-side​-encryption​-customer-algorithm header.

``--sse-customer-key-md5`` (string)
Specifies the 128-bit MD5 digest of the encryption key according to RFC 1321. Amazon S3 uses this header for a message integrity check to ensure the encryption key was transmitted without error.

``--ssekms-key-id`` (string)
Specifies the AWS KMS key ID to use for object encryption. All GET and PUT requests for an object protected by AWS KMS will fail if not made via SSL or using SigV4. Documentation on configuring any of the officially supported AWS SDKs and CLI can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingAWSSDK.html#specify-signature-version

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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command copies an object from ``bucket-1`` to ``bucket-2``::

  aws s3api copy-object --copy-source bucket-1/test.txt --key test.txt --bucket bucket-2

Output::

  {
      "CopyObjectResult": {
          "LastModified": "2015-11-10T01:07:25.000Z",
          "ETag": "\"589c8b79c230a6ecd5a7e1d040a9a030\""
      },
      "VersionId": "YdnYvTCVDqRRFA.NFJjy36p0hxifMlkA"
  }


======
Output
======

CopyObjectResult -> (structure)

  

  ETag -> (string)

    

    

  LastModified -> (timestamp)

    

    

  

Expiration -> (string)

  If the object expiration is configured, the response includes this header.

  

CopySourceVersionId -> (string)

  

  

VersionId -> (string)

  Version ID of the newly created copy.

  

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

  

