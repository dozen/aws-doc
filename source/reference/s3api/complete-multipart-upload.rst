[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api complete-multipart-upload:


*************************
complete-multipart-upload
*************************



===========
Description
===========

Completes a multipart upload by assembling previously uploaded parts.

========
Synopsis
========

::

    complete-multipart-upload
  --bucket <value>
  --key <value>
  [--multipart-upload <value>]
  --upload-id <value>
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--key`` (string)


``--multipart-upload`` (structure)




Shorthand Syntax::

    Parts=[{ETag=string,PartNumber=integer},{ETag=string,PartNumber=integer}]




JSON Syntax::

  {
    "Parts": [
      {
        "ETag": "string",
        "PartNumber": integer
      }
      ...
    ]
  }



``--upload-id`` (string)


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

The following command completes a multipart upload for the key ``multipart/01`` in the bucket ``my-bucket``::

  aws s3api complete-multipart-upload --multipart-upload file://mpustruct --bucket my-bucket --key 'multipart/01' --upload-id dfRtDYU0WWCCcH43C3WFbkRONycyCpTJJvxu2i5GYkZljF.Yxwh6XG7WfS2vC4to6HiV6Yjlx.cph0gtNBtJ8P3URCSbB7rjxI5iEwVDmgaXZOGgkk5nVTW16HOQ5l0R

The upload ID required by this command is output by ``create-multipart-upload`` and can also be retrieved with ``list-multipart-uploads``.

The multipart upload option in the above command takes a JSON structure that describes the parts of the multipart upload that should be reassembled into the complete file. In this example, the ``file://`` prefix is used to load the JSON structure from a file in the local folder named ``mpustruct``.

mpustruct::

  {
    "Parts": [
      {
        "ETag": "e868e0f4719e394144ef36531ee6824c",
        "PartNumber": 1
      },
      {
        "ETag": "6bb2b12753d66fe86da4998aa33fffb0",
        "PartNumber": 2
      },
      {
        "ETag": "d0a0112e841abec9c9ec83406f0159c8",
        "PartNumber": 3
      }
    ]
  }

The ETag value for each part is upload is output each time you upload a part using the ``upload-part`` command and can also be retrieved by calling ``list-parts`` or calculated by taking the MD5 checksum of each part.

Output::

  {
      "ETag": "\"3944a9f7a4faab7f78788ff6210f63f0-3\"",
      "Bucket": "my-bucket",
      "Location": "https://my-bucket.s3.amazonaws.com/multipart%2F01",
      "Key": "multipart/01"
  }


======
Output
======

Location -> (string)

  

  

Bucket -> (string)

  

  

Key -> (string)

  

  

Expiration -> (string)

  If the object expiration is configured, this will contain the expiration date (expiry-date) and rule ID (rule-id). The value of rule-id is URL encoded.

  

ETag -> (string)

  Entity tag of the object.

  

ServerSideEncryption -> (string)

  The Server-side encryption algorithm used when storing this object in S3 (e.g., AES256, aws:kms).

  

VersionId -> (string)

  Version of the object.

  

SSEKMSKeyId -> (string)

  If present, specifies the ID of the AWS Key Management Service (KMS) master encryption key that was used for the object.

  

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

