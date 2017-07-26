[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-lifecycle:


********************
put-bucket-lifecycle
********************



===========
Description
===========

Deprecated, see the put-bucket-lifecycle-configuration operation.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketLifecycle>`_


========
Synopsis
========

::

    put-bucket-lifecycle
  --bucket <value>
  [--content-md5 <value>]
  [--lifecycle-configuration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--content-md5`` (string)


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
        "Status": "Enabled"|"Disabled",
        "Transition": {
          "Date": timestamp,
          "Days": integer,
          "StorageClass": "GLACIER"|"STANDARD_IA"
        },
        "NoncurrentVersionTransition": {
          "NoncurrentDays": integer,
          "StorageClass": "GLACIER"|"STANDARD_IA"
        },
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

The following command applies a lifecycle configuration to the bucket ``my-bucket``::

  aws s3api put-bucket-lifecycle --bucket my-bucket --lifecycle-configuration file://lifecycle.json

The file ``lifecycle.json`` is a JSON document in the current folder that specifies two rules::

  {
    "Rules": [
      {
        "ID": "Move to Glacier after sixty days (objects in logs/2015/)",
        "Prefix": "logs/2015/",
        "Status": "Enabled",
        "Transition": {
          "Days": 60,
          "StorageClass": "GLACIER"
        }
      },
      {
        "Expiration": {
          "Date": "2016-01-01T00:00:00.000Z"
        },
        "ID": "Delete 2014 logs in 2016.",
        "Prefix": "logs/2014/",
        "Status": "Enabled"
      }
    ]
  }

The first rule moves files to Amazon Glacier after sixty days. The second rule deletes files from Amazon S3 on the specified date. For information on acceptable timestamp formats, see `Specifying Parameter Values`_ in the *AWS CLI User Guide*.

Each rule in the above example specifies a policy (``Transition`` or ``Expiration``) and file prefix (folder name) to which it applies. You can also create a rule that applies to an entire bucket by specifying a blank prefix::

  {
    "Rules": [
      {
        "ID": "Move to Glacier after sixty days (all objects in bucket)",
        "Prefix": "",
        "Status": "Enabled",
        "Transition": {
          "Days": 60,
          "StorageClass": "GLACIER"
        }
      }
    ]
  }

.. _`Specifying Parameter Values`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-param.html


======
Output
======

None