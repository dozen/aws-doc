[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api head-object:


***********
head-object
***********



===========
Description
===========

The HEAD operation retrieves metadata from an object without returning the object itself. This operation is useful if you're only interested in an object's metadata. To use HEAD, you must have READ access to the object.

========
Synopsis
========

::

    head-object
  --bucket <value>
  [--if-match <value>]
  [--if-modified-since <value>]
  [--if-none-match <value>]
  [--if-unmodified-since <value>]
  --key <value>
  [--range <value>]
  [--version-id <value>]
  [--sse-customer-algorithm <value>]
  [--sse-customer-key <value>]
  [--sse-customer-key-md5 <value>]
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--if-match`` (string)
Return the object only if its entity tag (ETag) is the same as the one specified, otherwise return a 412 (precondition failed).

``--if-modified-since`` (timestamp)
Return the object only if it has been modified since the specified time, otherwise return a 304 (not modified).

``--if-none-match`` (string)
Return the object only if its entity tag (ETag) is different from the one specified, otherwise return a 304 (not modified).

``--if-unmodified-since`` (timestamp)
Return the object only if it has not been modified since the specified time, otherwise return a 412 (precondition failed).

``--key`` (string)


``--range`` (string)
Downloads the specified range bytes of an object. For more information about the HTTP range header, go to http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.35.

``--version-id`` (string)
VersionId used to reference a specific version of the object.

``--sse-customer-algorithm`` (string)
Specifies the algorithm to use to when encrypting the object (e.g., AES256).

``--sse-customer-key`` (string)
Specifies the customer-provided encryption key for Amazon S3 to use in encrypting data. This value is used to store the object and then it is discarded; Amazon does not store the encryption key. The key must be appropriate for use with the algorithm specified in the x-amz-server-side​-encryption​-customer-algorithm header.

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

The following command retrieves metadata for an object in a bucket named ``my-bucket``::

  aws s3api head-object --bucket my-bucket --key index.html

Output::

  {
      "AcceptRanges": "bytes",
      "ContentType": "text/html",
      "LastModified": "Thu, 16 Apr 2015 18:19:14 GMT",
      "ContentLength": 77,
      "VersionId": "null",
      "ETag": "\"30a6ec7e1a9ad79c203d05a589c8b400\"",
      "Metadata": {}
  }

======
Output
======

DeleteMarker -> (boolean)

  Specifies whether the object retrieved was (true) or was not (false) a Delete Marker. If false, this response header does not appear in the response.

  

AcceptRanges -> (string)

  

  

Expiration -> (string)

  If the object expiration is configured (see PUT Bucket lifecycle), the response includes this header. It includes the expiry-date and rule-id key value pairs providing object expiration information. The value of the rule-id is URL encoded.

  

Restore -> (string)

  Provides information about object restoration operation and expiration time of the restored object copy.

  

LastModified -> (timestamp)

  Last modified date of the object

  

ContentLength -> (integer)

  Size of the body in bytes.

  

ETag -> (string)

  An ETag is an opaque identifier assigned by a web server to a specific version of a resource found at a URL

  

MissingMeta -> (integer)

  This is set to the number of metadata entries not returned in x-amz-meta headers. This can happen if you create metadata using an API like SOAP that supports more flexible metadata than the REST API. For example, using SOAP, you can create metadata whose values are not legal HTTP headers.

  

VersionId -> (string)

  Version of the object.

  

CacheControl -> (string)

  Specifies caching behavior along the request/reply chain.

  

ContentDisposition -> (string)

  Specifies presentational information for the object.

  

ContentEncoding -> (string)

  Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field.

  

ContentLanguage -> (string)

  The language the content is in.

  

ContentType -> (string)

  A standard MIME type describing the format of the object data.

  

Expires -> (timestamp)

  The date and time at which the object is no longer cacheable.

  

WebsiteRedirectLocation -> (string)

  If the bucket is configured as a website, redirects requests for this object to another object in the same bucket or to an external URL. Amazon S3 stores the value of this header in the object metadata.

  

ServerSideEncryption -> (string)

  The Server-side encryption algorithm used when storing this object in S3 (e.g., AES256, aws:kms).

  

Metadata -> (map)

  A map of metadata to store with the object in S3.

  key -> (string)

    

    

  value -> (string)

    

    

  

SSECustomerAlgorithm -> (string)

  If server-side encryption with a customer-provided encryption key was requested, the response will include this header confirming the encryption algorithm used.

  

SSECustomerKeyMD5 -> (string)

  If server-side encryption with a customer-provided encryption key was requested, the response will include this header to provide round trip message integrity verification of the customer-provided encryption key.

  

SSEKMSKeyId -> (string)

  If present, specifies the ID of the AWS Key Management Service (KMS) master encryption key that was used for the object.

  

StorageClass -> (string)

  

  

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

ReplicationStatus -> (string)

  

  

