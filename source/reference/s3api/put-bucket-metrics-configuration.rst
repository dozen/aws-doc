[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-metrics-configuration:


********************************
put-bucket-metrics-configuration
********************************



===========
Description
===========

Sets a metrics configuration (specified by the metrics configuration ID) for the bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketMetricsConfiguration>`_


========
Synopsis
========

::

    put-bucket-metrics-configuration
  --bucket <value>
  --id <value>
  --metrics-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
The name of the bucket for which the metrics configuration is set.

``--id`` (string)
The ID used to identify the metrics configuration.

``--metrics-configuration`` (structure)
Specifies the metrics configuration.



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