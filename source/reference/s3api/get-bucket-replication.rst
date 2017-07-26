[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-replication:


**********************
get-bucket-replication
**********************



===========
Description
===========

Returns the replication configuration of a bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetBucketReplication>`_


========
Synopsis
========

::

    get-bucket-replication
  --bucket <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command retrieves the replication configuration for a bucket named ``my-bucket``::

  aws s3api get-bucket-replication --bucket my-bucket

Output::

  {
      "ReplicationConfiguration": {
          "Rules": [
              {
                  "Status": "Enabled",
                  "Prefix": "",
                  "Destination": {
                      "Bucket": "arn:aws:s3:::my-bucket-backup",
                      "StorageClass": "STANDARD"
                  },
                  "ID": "ZmUwNzE4ZmQ4tMjVhOS00MTlkLOGI4NDkzZTIWJjNTUtYTA1"
              }
          ],
          "Role": "arn:aws:iam::123456789012:role/s3-replication-role"
      }
  }

======
Output
======

ReplicationConfiguration -> (structure)

  Container for replication rules. You can add as many as 1,000 rules. Total replication configuration size can be up to 2 MB.

  Role -> (string)

    Amazon Resource Name (ARN) of an IAM role for Amazon S3 to assume when replicating the objects.

    

  Rules -> (list)

    Container for information about a particular replication rule. Replication configuration must have at least one rule and can contain up to 1,000 rules.

    (structure)

      

      ID -> (string)

        Unique identifier for the rule. The value cannot be longer than 255 characters.

        

      Prefix -> (string)

        Object keyname prefix identifying one or more objects to which the rule applies. Maximum prefix length can be up to 1,024 characters. Overlapping prefixes are not supported.

        

      Status -> (string)

        The rule is ignored if status is not Enabled.

        

      Destination -> (structure)

        

        Bucket -> (string)

          Amazon resource name (ARN) of the bucket where you want Amazon S3 to store replicas of the object identified by the rule.

          

        StorageClass -> (string)

          The class of storage used to store the object.

          

        

      

    

  

