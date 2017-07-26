[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-replication:


**********************
put-bucket-replication
**********************



===========
Description
===========

Creates a new replication configuration (or replaces an existing one, if present).

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketReplication>`_


========
Synopsis
========

::

    put-bucket-replication
  --bucket <value>
  [--content-md5 <value>]
  --replication-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--content-md5`` (string)


``--replication-configuration`` (structure)
Container for replication rules. You can add as many as 1,000 rules. Total replication configuration size can be up to 2 MB.



JSON Syntax::

  {
    "Role": "string",
    "Rules": [
      {
        "ID": "string",
        "Prefix": "string",
        "Status": "Enabled"|"Disabled",
        "Destination": {
          "Bucket": "string",
          "StorageClass": "STANDARD"|"REDUCED_REDUNDANCY"|"STANDARD_IA"
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

The following command applies a replication configuration to a bucket named ``my-bucket``::

  aws s3api put-bucket-replication --bucket my-bucket --replication-configuration  file://replication.json

The file ``replication.json`` is a JSON document in the current folder that specifies a replication rule::

  {
    "Role": "arn:aws:iam::123456789012:role/s3-replication-role",
    "Rules": [
      {
        "Prefix": "",
        "Status": "Enabled",
        "Destination": {
          "Bucket": "arn:aws:s3:::my-bucket-backup",
          "StorageClass": "STANDARD"
        }
      }
    ]
  }

The destination bucket must be in a different region and have versioning enabled. The service role must have permission to write to the destination bucket and have a trust relationship that allows Amazon S3 to assume it.

Example service role permissions::

  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Effect": "Allow",
        "Action": "s3:*",
        "Resource": "*"
      }
    ]
  }

Trust relationship::

  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Effect": "Allow",
        "Principal": {
          "Service": "s3.amazonaws.com"
        },
        "Action": "sts:AssumeRole"
      }
    ]
  }


======
Output
======

None