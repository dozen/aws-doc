[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose update-destination:


******************
update-destination
******************



===========
Description
===========



Updates the specified destination of the specified delivery stream.

 

You can use this operation to change the destination type (for example, to replace the Amazon S3 destination with Amazon Redshift) or change the parameters associated with a destination (for example, to change the bucket name of the Amazon S3 destination). The update might not occur immediately. The target delivery stream remains active while the configurations are updated, so data writes to the delivery stream can continue during this process. The updated configurations are usually effective within a few minutes.

 

Note that switching between Amazon ES and other services is not supported. For an Amazon ES destination, you can only update to another Amazon ES destination.

 

If the destination type is the same, Firehose merges the configuration parameters specified with the destination configuration that already exists on the delivery stream. If any of the parameters are not specified in the call, the existing values are retained. For example, in the Amazon S3 destination, if  EncryptionConfiguration is not specified then the existing  EncryptionConfiguration is maintained on the destination.

 

If the destination type is not the same, for example, changing the destination from Amazon S3 to Amazon Redshift, Firehose does not merge any parameters. In this case, all parameters must be specified.

 

Firehose uses **CurrentDeliveryStreamVersionId** to avoid race conditions and conflicting merges. This is a required field, and the service updates the configuration only if the existing configuration has a version ID that matches. After the update is applied successfully, the version ID is updated, and can be retrieved using  describe-delivery-stream . You should use the new version ID to set **CurrentDeliveryStreamVersionId** in the next call.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/firehose-2015-08-04/UpdateDestination>`_


========
Synopsis
========

::

    update-destination
  --delivery-stream-name <value>
  --current-delivery-stream-version-id <value>
  --destination-id <value>
  [--s3-destination-update <value>]
  [--extended-s3-destination-update <value>]
  [--redshift-destination-update <value>]
  [--elasticsearch-destination-update <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--delivery-stream-name`` (string)


  The name of the delivery stream.

  

``--current-delivery-stream-version-id`` (string)


  Obtain this value from the **VersionId** result of  DeliveryStreamDescription . This value is required, and helps the service to perform conditional operations. For example, if there is a interleaving update and this value is null, then the update destination fails. After the update is successful, the **VersionId** value is updated. The service then performs a merge of the old configuration with the new configuration.

  

``--destination-id`` (string)


  The ID of the destination.

  

``--s3-destination-update`` (structure)


  [Deprecated] Describes an update for a destination in Amazon S3.

  



Shorthand Syntax::

    RoleARN=string,BucketARN=string,Prefix=string,BufferingHints={SizeInMBs=integer,IntervalInSeconds=integer},CompressionFormat=string,EncryptionConfiguration={NoEncryptionConfig=string,KMSEncryptionConfig={AWSKMSKeyARN=string}},CloudWatchLoggingOptions={Enabled=boolean,LogGroupName=string,LogStreamName=string}




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
    },
    "CloudWatchLoggingOptions": {
      "Enabled": true|false,
      "LogGroupName": "string",
      "LogStreamName": "string"
    }
  }



``--extended-s3-destination-update`` (structure)


  Describes an update for a destination in Amazon S3.

  



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
    },
    "CloudWatchLoggingOptions": {
      "Enabled": true|false,
      "LogGroupName": "string",
      "LogStreamName": "string"
    },
    "ProcessingConfiguration": {
      "Enabled": true|false,
      "Processors": [
        {
          "Type": "Lambda",
          "Parameters": [
            {
              "ParameterName": "LambdaArn"|"NumberOfRetries",
              "ParameterValue": "string"
            }
            ...
          ]
        }
        ...
      ]
    },
    "S3BackupMode": "Disabled"|"Enabled",
    "S3BackupUpdate": {
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
      },
      "CloudWatchLoggingOptions": {
        "Enabled": true|false,
        "LogGroupName": "string",
        "LogStreamName": "string"
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
    "RetryOptions": {
      "DurationInSeconds": integer
    },
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
      },
      "CloudWatchLoggingOptions": {
        "Enabled": true|false,
        "LogGroupName": "string",
        "LogStreamName": "string"
      }
    },
    "ProcessingConfiguration": {
      "Enabled": true|false,
      "Processors": [
        {
          "Type": "Lambda",
          "Parameters": [
            {
              "ParameterName": "LambdaArn"|"NumberOfRetries",
              "ParameterValue": "string"
            }
            ...
          ]
        }
        ...
      ]
    },
    "S3BackupMode": "Disabled"|"Enabled",
    "S3BackupUpdate": {
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
      },
      "CloudWatchLoggingOptions": {
        "Enabled": true|false,
        "LogGroupName": "string",
        "LogStreamName": "string"
      }
    },
    "CloudWatchLoggingOptions": {
      "Enabled": true|false,
      "LogGroupName": "string",
      "LogStreamName": "string"
    }
  }



``--elasticsearch-destination-update`` (structure)


  Describes an update for a destination in Amazon ES.

  



JSON Syntax::

  {
    "RoleARN": "string",
    "DomainARN": "string",
    "IndexName": "string",
    "TypeName": "string",
    "IndexRotationPeriod": "NoRotation"|"OneHour"|"OneDay"|"OneWeek"|"OneMonth",
    "BufferingHints": {
      "IntervalInSeconds": integer,
      "SizeInMBs": integer
    },
    "RetryOptions": {
      "DurationInSeconds": integer
    },
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
      },
      "CloudWatchLoggingOptions": {
        "Enabled": true|false,
        "LogGroupName": "string",
        "LogStreamName": "string"
      }
    },
    "ProcessingConfiguration": {
      "Enabled": true|false,
      "Processors": [
        {
          "Type": "Lambda",
          "Parameters": [
            {
              "ParameterName": "LambdaArn"|"NumberOfRetries",
              "ParameterValue": "string"
            }
            ...
          ]
        }
        ...
      ]
    },
    "CloudWatchLoggingOptions": {
      "Enabled": true|false,
      "LogGroupName": "string",
      "LogStreamName": "string"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

