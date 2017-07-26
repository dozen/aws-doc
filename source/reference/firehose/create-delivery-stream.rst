[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose create-delivery-stream:


**********************
create-delivery-stream
**********************



===========
Description
===========



Creates a delivery stream.

 

By default, you can create up to 20 delivery streams per region.

 

This is an asynchronous operation that immediately returns. The initial status of the delivery stream is ``CREATING`` . After the delivery stream is created, its status is ``ACTIVE`` and it now accepts data. Attempts to send data to a delivery stream that is not in the ``ACTIVE`` state cause an exception. To check the state of a delivery stream, use  describe-delivery-stream .

 

A delivery stream is configured with a single destination: Amazon S3, Amazon Elasticsearch Service, or Amazon Redshift. You must specify only one of the following destination configuration parameters: **extended-s3-destination-configuration** , **s3-destination-configuration** , **elasticsearch-destination-configuration** , or **redshift-destination-configuration** .

 

When you specify **s3-destination-configuration** , you can also provide the following optional values: **BufferingHints** , **EncryptionConfiguration** , and **CompressionFormat** . By default, if no **BufferingHints** value is provided, Firehose buffers data up to 5 MB or for 5 minutes, whichever condition is satisfied first. Note that **BufferingHints** is a hint, so there are some cases where the service cannot adhere to these conditions strictly; for example, record boundaries are such that the size is a little over or under the configured buffering size. By default, no encryption is performed. We strongly recommend that you enable encryption to ensure secure data storage in Amazon S3.

 

A few notes about Amazon Redshift as a destination:

 

 
* An Amazon Redshift destination requires an S3 bucket as intermediate location, as Firehose first delivers data to S3 and then uses ``COPY`` syntax to load data into an Amazon Redshift table. This is specified in the **RedshiftDestinationConfiguration.S3Configuration** parameter. 
 
* The compression formats ``SNAPPY`` or ``ZIP`` cannot be specified in **RedshiftDestinationConfiguration.S3Configuration** because the Amazon Redshift ``COPY`` operation that reads from the S3 bucket doesn't support these compression formats. 
 
* We strongly recommend that you use the user name and password you provide exclusively with Firehose, and that the permissions for the account are restricted for Amazon Redshift ``INSERT`` permissions. 
 

 

Firehose assumes the IAM role that is configured as part of the destination. The role should allow the Firehose principal to assume the role, and the role should have permissions that allows the service to deliver the data. For more information, see `Amazon S3 Bucket Access <http://docs.aws.amazon.com/firehose/latest/dev/controlling-access.html#using-iam-s3>`_ in the *Amazon Kinesis Firehose Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/firehose-2015-08-04/CreateDeliveryStream>`_


========
Synopsis
========

::

    create-delivery-stream
  --delivery-stream-name <value>
  [--s3-destination-configuration <value>]
  [--extended-s3-destination-configuration <value>]
  [--redshift-destination-configuration <value>]
  [--elasticsearch-destination-configuration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--delivery-stream-name`` (string)


  The name of the delivery stream. This name must be unique per AWS account in the same region. You can have multiple delivery streams with the same name if they are in different accounts or different regions.

  

``--s3-destination-configuration`` (structure)


  [Deprecated] The destination in Amazon S3. You can specify only one destination.

  



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



``--extended-s3-destination-configuration`` (structure)


  The destination in Amazon S3. You can specify only one destination.

  



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
    "S3BackupConfiguration": {
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



``--redshift-destination-configuration`` (structure)


  The destination in Amazon Redshift. You can specify only one destination.

  



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
    "S3BackupConfiguration": {
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



``--elasticsearch-destination-configuration`` (structure)


  The destination in Amazon ES. You can specify only one destination.

  



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
    "S3BackupMode": "FailedDocumentsOnly"|"AllDocuments",
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

DeliveryStreamARN -> (string)

  

  The ARN of the delivery stream.

  

  

