[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api list-parts:


**********
list-parts
**********



===========
Description
===========

Lists the parts that have been uploaded for a specific multipart upload.

``list-parts`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Parts``


========
Synopsis
========

::

    list-parts
  --bucket <value>
  --key <value>
  --upload-id <value>
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--key`` (string)


``--upload-id`` (string)
Upload ID identifying the multipart upload whose parts are being listed.

``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the request. Bucket owners need not specify this parameter in their requests. Documentation on downloading objects from requester pays buckets can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectsinRequesterPaysBuckets.html

  Possible values:

  
  *   ``requester``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command lists all of the parts that have been uploaded for a multipart upload with key ``multipart/01`` in the bucket ``my-bucket``::

  aws s3api list-parts --bucket my-bucket --key 'multipart/01' --upload-id dfRtDYU0WWCCcH43C3WFbkRONycyCpTJJvxu2i5GYkZljF.Yxwh6XG7WfS2vC4to6HiV6Yjlx.cph0gtNBtJ8P3URCSbB7rjxI5iEwVDmgaXZOGgkk5nVTW16HOQ5l0R

Output::

  {
      "Owner": {
          "DisplayName": "aws-account-name",
          "ID": "100719349fc3b6dcd7c820a124bf7aecd408092c3d7b51b38494939801fc248b"
      },
      "Initiator": {
          "DisplayName": "username",
          "ID": "arn:aws:iam::0123456789012:user/username"
      },
      "Parts": [
          {
              "LastModified": "2015-06-02T18:07:35.000Z",
              "PartNumber": 1,
              "ETag": "\"e868e0f4719e394144ef36531ee6824c\"",
              "Size": 5242880
          },
          {
              "LastModified": "2015-06-02T18:07:42.000Z",
              "PartNumber": 2,
              "ETag": "\"6bb2b12753d66fe86da4998aa33fffb0\"",
              "Size": 5242880
          },
          {
              "LastModified": "2015-06-02T18:07:47.000Z",
              "PartNumber": 3,
              "ETag": "\"d0a0112e841abec9c9ec83406f0159c8\"",
              "Size": 5242880
          }
      ],
      "StorageClass": "STANDARD"
  }

======
Output
======

Bucket -> (string)

  Name of the bucket to which the multipart upload was initiated.

  

Key -> (string)

  Object key for which the multipart upload was initiated.

  

UploadId -> (string)

  Upload ID identifying the multipart upload whose parts are being listed.

  

PartNumberMarker -> (integer)

  Part number after which listing begins.

  

NextPartNumberMarker -> (integer)

  When a list is truncated, this element specifies the last part in the list, as well as the value to use for the part-number-marker request parameter in a subsequent request.

  

MaxParts -> (integer)

  Maximum number of parts that were allowed in the response.

  

IsTruncated -> (boolean)

  Indicates whether the returned list of parts is truncated.

  

Parts -> (list)

  

  (structure)

    

    PartNumber -> (integer)

      Part number identifying the part. This is a positive integer between 1 and 10,000.

      

    LastModified -> (timestamp)

      Date and time at which the part was uploaded.

      

    ETag -> (string)

      Entity tag returned when the part was uploaded.

      

    Size -> (integer)

      Size of the uploaded part data.

      

    

  

Initiator -> (structure)

  Identifies who initiated the multipart upload.

  ID -> (string)

    If the principal is an AWS account, it provides the Canonical User ID. If the principal is an IAM User, it provides a user ARN value.

    

  DisplayName -> (string)

    Name of the Principal.

    

  

Owner -> (structure)

  

  DisplayName -> (string)

    

    

  ID -> (string)

    

    

  

StorageClass -> (string)

  The class of storage used to store the object.

  

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

