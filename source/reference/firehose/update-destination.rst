[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose update-destination:


******************
update-destination
******************



===========
Description
===========



Updates the specified destination of the specified delivery stream. 

 

This operation can be used to change the destination type (for example, to replace the Amazon S3 destination with Amazon Redshift) or change the parameters associated with a given destination (for example, to change the bucket name of the Amazon S3 destination). The update may not occur immediately. The target delivery stream remains active while the configurations are updated, so data writes to the delivery stream can continue during this process. The updated configurations are normally effective within a few minutes. 

 

If the destination type is the same, Amazon Kinesis Firehose merges the configuration parameters specified in the  update-destination request with the destination configuration that already exists on the delivery stream. If any of the parameters are not specified in the update request, then the existing configuration parameters are retained. For example, in the Amazon S3 destination, if  EncryptionConfiguration is not specified then the existing  EncryptionConfiguration is maintained on the destination.

 

If the destination type is not the same, for example, changing the destination from Amazon S3 to Amazon Redshift, Amazon Kinesis Firehose does not merge any parameters. In this case, all parameters must be specified.

 

Amazon Kinesis Firehose uses the ``CurrentDeliveryStreamVersionId`` to avoid race conditions and conflicting merges. This is a required field in every request and the service only updates the configuration if the existing configuration matches the ``VersionId`` . After the update is applied successfully, the ``VersionId`` is updated, which can be retrieved with the  describe-delivery-stream operation. The new ``VersionId`` should be uses to set ``CurrentDeliveryStreamVersionId`` in the next  update-destination operation.



========
Synopsis
========

::

    update-destination
  --delivery-stream-name <value>
  --current-delivery-stream-version-id <value>
  --destination-id <value>
  [--s3-destination-update <value>]
  [--redshift-destination-update <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--delivery-stream-name`` (string)


  The name of the delivery stream.

  

``--current-delivery-stream-version-id`` (string)


  Obtain this value from the ``VersionId`` result of the  DeliveryStreamDescription operation. This value is required, and helps the service to perform conditional operations. For example, if there is a interleaving update and this value is null, then the update destination fails. After the update is successful, the ``VersionId`` value is updated. The service then performs a merge of the old configuration with the new configuration.

  

``--destination-id`` (string)


  The ID of the destination.

  

``--s3-destination-update`` (structure)


  Describes an update for a destination in Amazon S3.

  



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



``--redshift-destination-update`` (structure)


  Describes an update for a destination in Amazon Redshift.

  



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
    "S3Update": {
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

