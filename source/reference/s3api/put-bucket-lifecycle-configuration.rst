[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-lifecycle-configuration:


**********************************
put-bucket-lifecycle-configuration
**********************************



===========
Description
===========

Sets lifecycle configuration for your bucket. If a lifecycle configuration exists, it replaces it.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketLifecycleConfiguration>`_


========
Synopsis
========

::

    put-bucket-lifecycle-configuration
  --bucket <value>
  [--lifecycle-configuration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--lifecycle-configuration`` (structure)




JSON Syntax::

  {
    "Rules": [
      {
        "Expiration": {
          "Date": timestamp,
          "Days": integer,
          "ExpiredObjectDeleteMarker": true|false
        },
        "ID": "string",
        "Prefix": "string",
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
        "Status": "Enabled"|"Disabled",
        "Transitions": [
          {
            "Date": timestamp,
            "Days": integer,
            "StorageClass": "GLACIER"|"STANDARD_IA"
          }
          ...
        ],
        "NoncurrentVersionTransitions": [
          {
            "NoncurrentDays": integer,
            "StorageClass": "GLACIER"|"STANDARD_IA"
          }
          ...
        ],
        "NoncurrentVersionExpiration": {
          "NoncurrentDays": integer
        },
        "AbortIncompleteMultipartUpload": {
          "DaysAfterInitiation": integer
        }
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command applies a lifecycle configuration to a bucket named ``my-bucket``::

  aws s3api put-bucket-lifecycle-configuration --bucket my-bucket --lifecycle-configuration  file://lifecycle.json

The file ``lifecycle.json`` is a JSON document in the current folder that specifies two rules::

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
                      "NoncurrentDays": 2,
                      "StorageClass": "GLACIER"
                  }
              ],
              "ID": "Move old versions to Glacier"
          }
      ]
  }

The first rule moves files with the prefix ``rotated`` to Glacier on the specified date. The second rule moves old object versions to Glacier when they are no longer current. For information on acceptable timestamp formats, see `Specifying Parameter Values`_ in the *AWS CLI User Guide*.

.. _`Specifying Parameter Values`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-param.html

======
Output
======

None