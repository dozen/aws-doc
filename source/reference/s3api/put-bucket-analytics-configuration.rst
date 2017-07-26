[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-analytics-configuration:


**********************************
put-bucket-analytics-configuration
**********************************



===========
Description
===========

Sets an analytics configuration for the bucket (specified by the analytics configuration ID).

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketAnalyticsConfiguration>`_


========
Synopsis
========

::

    put-bucket-analytics-configuration
  --bucket <value>
  --id <value>
  --analytics-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
The name of the bucket to which an analytics configuration is stored.

``--id`` (string)
The identifier used to represent an analytics configuration.

``--analytics-configuration`` (structure)
The configuration and any analyses for the analytics filter.



JSON Syntax::

  {
    "Id": "string",
    "Filter": {
      "Prefix": "string",
      "Tag": {
        "Key": "string",
        "Value": "string"
      },
      "And": {
        "Prefix": "string",
        "Tags": [
          {
            "Key": "string",
            "Value": "string"
          }
          ...
        ]
      }
    },
    "StorageClassAnalysis": {
      "DataExport": {
        "OutputSchemaVersion": "V_1",
        "Destination": {
          "S3BucketDestination": {
            "Format": "CSV",
            "BucketAccountId": "string",
            "Bucket": "string",
            "Prefix": "string"
          }
        }
      }
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None