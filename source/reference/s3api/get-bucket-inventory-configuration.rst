[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-inventory-configuration:


**********************************
get-bucket-inventory-configuration
**********************************



===========
Description
===========

Returns an inventory configuration (identified by the inventory ID) from the bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetBucketInventoryConfiguration>`_


========
Synopsis
========

::

    get-bucket-inventory-configuration
  --bucket <value>
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
The name of the bucket containing the inventory configuration to retrieve.

``--id`` (string)
The ID used to identify the inventory configuration.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

InventoryConfiguration -> (structure)

  Specifies the inventory configuration.

  Destination -> (structure)

    Contains information about where to publish the inventory results.

    S3BucketDestination -> (structure)

      Contains the bucket name, file format, bucket owner (optional), and prefix (optional) where inventory results are published.

      AccountId -> (string)

        The ID of the account that owns the destination bucket.

        

      Bucket -> (string)

        The Amazon resource name (ARN) of the bucket where inventory results will be published.

        

      Format -> (string)

        Specifies the output format of the inventory results.

        

      Prefix -> (string)

        The prefix that is prepended to all inventory results.

        

      

    

  IsEnabled -> (boolean)

    Specifies whether the inventory is enabled or disabled.

    

  Filter -> (structure)

    Specifies an inventory filter. The inventory only includes objects that meet the filter's criteria.

    Prefix -> (string)

      The prefix that an object must have to be included in the inventory results.

      

    

  Id -> (string)

    The ID used to identify the inventory configuration.

    

  IncludedObjectVersions -> (string)

    Specifies which object version(s) to included in the inventory results.

    

  OptionalFields -> (list)

    Contains the optional fields that are included in the inventory results.

    (string)

      

      

    

  Schedule -> (structure)

    Specifies the schedule for generating inventory results.

    Frequency -> (string)

      Specifies how frequently inventory results are produced.

      

    

  

