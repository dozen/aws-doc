[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-inventory-configuration:


**********************************
put-bucket-inventory-configuration
**********************************



===========
Description
===========

Adds an inventory configuration (identified by the inventory ID) from the bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketInventoryConfiguration>`_


========
Synopsis
========

::

    put-bucket-inventory-configuration
  --bucket <value>
  --id <value>
  --inventory-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
The name of the bucket where the inventory configuration will be stored.

``--id`` (string)
The ID used to identify the inventory configuration.

``--inventory-configuration`` (structure)
Specifies the inventory configuration.



Shorthand Syntax::

    Destination={S3BucketDestination={AccountId=string,Bucket=string,Format=string,Prefix=string}},IsEnabled=boolean,Filter={Prefix=string},Id=string,IncludedObjectVersions=string,OptionalFields=string,string,Schedule={Frequency=string}




JSON Syntax::

  {
    "Destination": {
      "S3BucketDestination": {
        "AccountId": "string",
        "Bucket": "string",
        "Format": "CSV",
        "Prefix": "string"
      }
    },
    "IsEnabled": true|false,
    "Filter": {
      "Prefix": "string"
    },
    "Id": "string",
    "IncludedObjectVersions": "All"|"Current",
    "OptionalFields": ["Size"|"LastModifiedDate"|"StorageClass"|"ETag"|"IsMultipartUploaded"|"ReplicationStatus", ...],
    "Schedule": {
      "Frequency": "Daily"|"Weekly"
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