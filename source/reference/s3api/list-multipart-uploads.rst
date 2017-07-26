[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api list-multipart-uploads:


**********************
list-multipart-uploads
**********************



===========
Description
===========

This operation lists in-progress multipart uploads.

``list-multipart-uploads`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Uploads``, ``CommonPrefixes``


========
Synopsis
========

::

    list-multipart-uploads
  --bucket <value>
  [--delimiter <value>]
  [--encoding-type <value>]
  [--prefix <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--delimiter`` (string)
Character you use to group keys.

``--encoding-type`` (string)
Requests Amazon S3 to encode the object keys in the response and specifies the encoding method to use. An object key may contain any Unicode character; however, XML 1.0 parser cannot parse some characters, such as characters with an ASCII value from 0 to 10. For characters that are not supported in XML 1.0, you can add this parameter to request that Amazon S3 encode the keys in the response.

  Possible values:

  
  *   ``url``

  

  

``--prefix`` (string)
Lists in-progress uploads only for those keys that begin with the specified prefix.

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

The following command lists all of the active multipart uploads for a bucket named ``my-bucket``::

  aws s3api list-multipart-uploads --bucket my-bucket

Output::

  {
      "Uploads": [
          {
              "Initiator": {
                  "DisplayName": "username",
                  "ID": "arn:aws:iam::0123456789012:user/username"
              },
              "Initiated": "2015-06-02T18:01:30.000Z",
              "UploadId": "dfRtDYU0WWCCcH43C3WFbkRONycyCpTJJvxu2i5GYkZljF.Yxwh6XG7WfS2vC4to6HiV6Yjlx.cph0gtNBtJ8P3URCSbB7rjxI5iEwVDmgaXZOGgkk5nVTW16HOQ5l0R",
              "StorageClass": "STANDARD",
              "Key": "multipart/01",
              "Owner": {
                  "DisplayName": "aws-account-name",
                  "ID": "100719349fc3b6dcd7c820a124bf7aecd408092c3d7b51b38494939801fc248b"
              }
          }
      ],
      "CommonPrefixes": []
  }

In progress multipart uploads incur storage costs in Amazon S3. Complete or abort an active multipart upload to remove its parts from your account.

======
Output
======

Bucket -> (string)

  Name of the bucket to which the multipart upload was initiated.

  

KeyMarker -> (string)

  The key at or after which the listing began.

  

UploadIdMarker -> (string)

  Upload ID after which listing began.

  

NextKeyMarker -> (string)

  When a list is truncated, this element specifies the value that should be used for the key-marker request parameter in a subsequent request.

  

Prefix -> (string)

  When a prefix is provided in the request, this field contains the specified prefix. The result contains only keys starting with the specified prefix.

  

Delimiter -> (string)

  

  

NextUploadIdMarker -> (string)

  When a list is truncated, this element specifies the value that should be used for the upload-id-marker request parameter in a subsequent request.

  

MaxUploads -> (integer)

  Maximum number of multipart uploads that could have been included in the response.

  

IsTruncated -> (boolean)

  Indicates whether the returned list of multipart uploads is truncated. A value of true indicates that the list was truncated. The list can be truncated if the number of multipart uploads exceeds the limit allowed or specified by max uploads.

  

Uploads -> (list)

  

  (structure)

    

    UploadId -> (string)

      Upload ID that identifies the multipart upload.

      

    Key -> (string)

      Key of the object for which the multipart upload was initiated.

      

    Initiated -> (timestamp)

      Date and time at which the multipart upload was initiated.

      

    StorageClass -> (string)

      The class of storage used to store the object.

      

    Owner -> (structure)

      

      DisplayName -> (string)

        

        

      ID -> (string)

        

        

      

    Initiator -> (structure)

      Identifies who initiated the multipart upload.

      ID -> (string)

        If the principal is an AWS account, it provides the Canonical User ID. If the principal is an IAM User, it provides a user ARN value.

        

      DisplayName -> (string)

        Name of the Principal.

        

      

    

  

CommonPrefixes -> (list)

  

  (structure)

    

    Prefix -> (string)

      

      

    

  

EncodingType -> (string)

  Encoding type used by Amazon S3 to encode object keys in the response.

  

