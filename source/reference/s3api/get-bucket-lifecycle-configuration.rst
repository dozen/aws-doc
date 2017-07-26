[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-lifecycle-configuration:


**********************************
get-bucket-lifecycle-configuration
**********************************



===========
Description
===========

Returns the lifecycle configuration information set on the bucket.

========
Synopsis
========

::

    get-bucket-lifecycle-configuration
  --bucket <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

        

      

    ID -> (string)

      Unique identifier for the rule. The value cannot be longer than 255 characters.

      

    Prefix -> (string)

      Prefix identifying one or more objects to which the rule applies.

      

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

          Specifies the number of days an object is noncurrent before Amazon S3 can perform the associated action. For information about the noncurrent days calculations, see `How Amazon S3 Calculates When an Object Became Noncurrent`_ in the Amazon Simple Storage Service Developer Guide.

          

        StorageClass -> (string)

          The class of storage used to store the object.

          

        

      

    NoncurrentVersionExpiration -> (structure)

      Specifies when noncurrent object versions expire. Upon expiration, Amazon S3 permanently deletes the noncurrent object versions. You set this lifecycle configuration action on a bucket that has versioning enabled (or suspended) to request that Amazon S3 delete noncurrent object versions at a specific period in the object's lifetime.

      NoncurrentDays -> (integer)

        Specifies the number of days an object is noncurrent before Amazon S3 can perform the associated action. For information about the noncurrent days calculations, see `How Amazon S3 Calculates When an Object Became Noncurrent`_ in the Amazon Simple Storage Service Developer Guide.

        

      

    

  



.. _How Amazon S3 Calculates When an Object Became Noncurrent: /AmazonS3/latest/dev/s3-access-control.html
