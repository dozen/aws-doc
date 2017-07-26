[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose create-delivery-stream:


**********************
create-delivery-stream
**********************



===========
Description
===========



Creates a delivery stream.

 

 create-delivery-stream is an asynchronous operation that immediately returns. The initial status of the delivery stream is ``CREATING`` . After the delivery stream is created, its status is ``ACTIVE`` and it now accepts data. Attempts to send data to a delivery stream that is not in the ``ACTIVE`` state cause an exception. To check the state of a delivery stream, use  describe-delivery-stream .

 

The name of a delivery stream identifies it. You can't have two delivery streams with the same name in the same region. Two delivery streams in different AWS accounts or different regions in the same AWS account can have the same name.

 

By default, you can create up to 5 delivery streams per region.

 

A delivery stream can only be configured with a single destination, Amazon S3 or Amazon Redshift. For correct  create-delivery-stream request syntax, specify only one destination configuration parameter: either ``redshift-destination-configuration`` or ``s3-destination-configuration`` 

 

As part of ``s3-destination-configuration`` , optional values ``BufferingHints`` , ``EncryptionConfiguration`` , and ``CompressionFormat`` can be provided. By default, if no ``BufferingHints`` value is provided, Amazon Kinesis Firehose buffers data up to 5 MB or for 5 minutes, whichever condition is satisfied first. Note that ``BufferingHints`` is a hint, so there are some cases where the service cannot adhere to these conditions strictly; for example, record boundaries are such that the size is a little over or under the configured buffering size. By default, no encryption is performed. We strongly recommend that you enable encryption to ensure secure data storage in Amazon S3.

 

A few notes about ``redshift-destination-configuration`` :

 

 
* An Amazon Redshift destination requires an S3 bucket as intermediate location, as Amazon Kinesis Firehose first delivers data to S3 and then uses ``COPY`` syntax to load data into an Amazon Redshift table. This is specified in the ``RedshiftDestinationConfiguration.S3Configuration`` parameter element.
 
* The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified in ``RedshiftDestinationConfiguration.S3Configuration`` because the Amazon Redshift ``COPY`` operation that reads from the S3 bucket doesn't support these compression formats.
 
* We strongly recommend that the username and password provided is used exclusively for Amazon Kinesis Firehose purposes, and that the permissions for the account are restricted for Amazon Redshift ``INSERT`` permissions.
 

 

Amazon Kinesis Firehose assumes the IAM role that is configured as part of destinations. The IAM role should allow the Amazon Kinesis Firehose principal to assume the role, and the role should have permissions that allows the service to deliver the data. For more information, see `Amazon S3 Bucket Access`_ in the *Amazon Kinesis Firehose Developer Guide* .



========
Synopsis
========

::

    create-delivery-stream
  --delivery-stream-name <value>
  [--s3-destination-configuration <value>]
  [--redshift-destination-configuration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--delivery-stream-name`` (string)


  The name of the delivery stream.

  

``--s3-destination-configuration`` (structure)


  The destination in Amazon S3. This value must be specified if ``redshift-destination-configuration`` is specified (see restrictions listed above).

  



Shorthand Syntax::

    RoleARN=string,BucketARN=string,Prefix=string,BufferingHints={SizeInMBs=integer,IntervalInSeconds=integer},CompressionFormat=string,EncryptionConfiguration={NoEncryptionConfig=string,KMSEncryptionConfig={AWSKMSKeyARN=string}}




JSON Syntax::

  {
    "RoleARN": "string",
    "BucketARN": "string",
    "Prefix": "string",
    "BufferingHints": {
      "SizeInMBs": integer,
      "IntervalInSeconds": integer
    },
    "CompressionFormat": "UNCOMPRESSED"|"GZIP"|"ZIP"|"Snappy",
    "EncryptionConfiguration": {
      "NoEncryptionConfig": "NoEncryption",
      "KMSEncryptionConfig": {
        "AWSKMSKeyARN": "string"
      }
    }
  }



``--redshift-destination-configuration`` (structure)


  The destination in Amazon Redshift. This value cannot be specified if Amazon S3 is the desired destination (see restrictions listed above).

  



JSON Syntax::

  {
    "RoleARN": "string",
    "ClusterJDBCURL": "string",
    "CopyCommand": {
      "DataTableName": "string",
      "DataTableColumns": "string",
      "CopyOptions": "string"
    },
    "Username": "string",
    "Password": "string",
    "S3Configuration": {
      "RoleARN": "string",
      "BucketARN": "string",
      "Prefix": "string",
      "BufferingHints": {
        "SizeInMBs": integer,
        "IntervalInSeconds": integer
      },
      "CompressionFormat": "UNCOMPRESSED"|"GZIP"|"ZIP"|"Snappy",
      "EncryptionConfiguration": {
        "NoEncryptionConfig": "NoEncryption",
        "KMSEncryptionConfig": {
          "AWSKMSKeyARN": "string"
        }
      }
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DeliveryStreamARN -> (string)

  

  The ARN of the delivery stream.

  

  



.. _Amazon S3 Bucket Access: http://docs.aws.amazon.com/firehose/latest/dev/controlling-access.html#using-iam-s3
