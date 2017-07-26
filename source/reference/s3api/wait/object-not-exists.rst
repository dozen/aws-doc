[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` . :ref:`wait <cli:aws s3api wait>` ]

.. _cli:aws s3api wait object-not-exists:


*****************
object-not-exists
*****************



===========
Description
===========

Wait until 404 response is received when polling with ``head-object``. It will poll every 5 seconds until a successful state has been reached. This will exit with a return code of 255 after 20 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/HeadObject>`_


========
Synopsis
========

::

    object-not-exists
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
  [--part-number <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

  

  

``--part-number`` (integer)
Part number of the object being read. This is a positive integer between 1 and 10,000. Effectively performs a 'ranged' HEAD request for the part specified. Useful querying about the size of the part and the number of parts in this object.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None