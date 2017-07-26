[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-lifecycle-configuration:


**********************************
get-bucket-lifecycle-configuration
**********************************



===========
Description
===========

Returns the lifecycle configuration information set on the bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetBucketLifecycleConfiguration>`_


========
Synopsis
========

::

    get-bucket-lifecycle-configuration
  --bucket <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command retrieves the lifecycle configuration for a bucket named ``my-bucket``::

  aws s3api get-bucket-lifecycle-configuration --bucket my-bucket

Output::

  {
      "Rules": [
          {
              "ID": "Move rotated logs to Glacier",
              "Prefix": "rotated/",
              "Status": "Enabled",
              "Transitions": [
                  {
                      "Date": "2015-11-10T00:00:00.000Z",
                      "StorageClass": "GLACIER"
                  }
              ]
          },
          {
              "Status": "Enabled",
              "Prefix": "",
              "NoncurrentVersionTransitions": [
                  {
                      "NoncurrentDays": 0,
                      "StorageClass": "GLACIER"
                  }
              ],
              "ID": "Move old versions to Glacier"
          }
      ]
  }

======
Output
======

Rules -> (list)

  

  (structure)

    

    Expiration -> (structure)

      

      Date -> (timestamp)

        Indicates at what date the object is to be moved or deleted. Should be in GMT ISO 8601 Format.

        

      Days -> (integer)

        Indicates the lifetime, in days, of the objects that are subject to the rule. The value must be a non-zero positive integer.

        

      ExpiredObjectDeleteMarker -> (boolean)

        Indicates whether Amazon S3 will remove a delete marker with no noncurrent versions. If set to true, the delete marker will be expired; if set to false the policy takes no action. This cannot be specified with Days or Date in a Lifecycle Expiration Policy.

        

      

    ID -> (string)

      Unique identifier for the rule. The value cannot be longer than 255 characters.

      

    Prefix -> (string)

      Prefix identifying one or more objects to which the rule applies. This is deprecated; use Filter instead.

      

    Filter -> (structure)

      The Filter is used to identify objects that a Lifecycle Rule applies to. A Filter must have exactly one of Prefix, Tag, or And specified.

      Prefix -> (string)

        Prefix identifying one or more objects to which the rule applies.

        

      Tag -> (structure)

        This tag must exist in the object's tag set in order for the rule to apply.

        Key -> (string)

          Name of the tag.

          

        Value -> (string)

          Value of the tag.

          

        

      And -> (structure)

        This is used in a Lifecycle Rule Filter to apply a logical AND to two or more predicates. The Lifecycle Rule will apply to any object matching all of the predicates configured inside the And operator.

        Prefix -> (string)

          

          

        Tags -> (list)

          All of these tags must exist in the object's tag set in order for the rule to apply.

          (structure)

            

            Key -> (string)

              Name of the tag.

              

            Value -> (string)

              Value of the tag.

              

            

          

        

      

    Status -> (string)

      If 'Enabled', the rule is currently being applied. If 'Disabled', the rule is not currently being applied.

      

    Transitions -> (list)

      

      (structure)

        

        Date -> (timestamp)

          Indicates at what date the object is to be moved or deleted. Should be in GMT ISO 8601 Format.

          

        Days -> (integer)

          Indicates the lifetime, in days, of the objects that are subject to the rule. The value must be a non-zero positive integer.

          

        StorageClass -> (string)

          The class of storage used to store the object.

          

        

      

    NoncurrentVersionTransitions -> (list)

      

      (structure)

        Container for the transition rule that describes when noncurrent objects transition to the STANDARD_IA or GLACIER storage class. If your bucket is versioning-enabled (or versioning is suspended), you can set this action to request that Amazon S3 transition noncurrent object versions to the STANDARD_IA or GLACIER storage class at a specific period in the object's lifetime.

        NoncurrentDays -> (integer)

          Specifies the number of days an object is noncurrent before Amazon S3 can perform the associated action. For information about the noncurrent days calculations, see `How Amazon S3 Calculates When an Object Became Noncurrent <http://docs.aws.amazon.com/AmazonS3/latest/dev/s3-access-control.html>`_ in the Amazon Simple Storage Service Developer Guide.

          

        StorageClass -> (string)

          The class of storage used to store the object.

          

        

      

    NoncurrentVersionExpiration -> (structure)

      Specifies when noncurrent object versions expire. Upon expiration, Amazon S3 permanently deletes the noncurrent object versions. You set this lifecycle configuration action on a bucket that has versioning enabled (or suspended) to request that Amazon S3 delete noncurrent object versions at a specific period in the object's lifetime.

      NoncurrentDays -> (integer)

        Specifies the number of days an object is noncurrent before Amazon S3 can perform the associated action. For information about the noncurrent days calculations, see `How Amazon S3 Calculates When an Object Became Noncurrent <http://docs.aws.amazon.com/AmazonS3/latest/dev/s3-access-control.html>`_ in the Amazon Simple Storage Service Developer Guide.

        

      

    AbortIncompleteMultipartUpload -> (structure)

      Specifies the days since the initiation of an Incomplete Multipart Upload that Lifecycle will wait before permanently removing all parts of the upload.

      DaysAfterInitiation -> (integer)

        Indicates the number of days that must pass since initiation for Lifecycle to abort an Incomplete Multipart Upload.

        

      

    

  

