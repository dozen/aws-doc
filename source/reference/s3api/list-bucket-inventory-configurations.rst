[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api list-bucket-inventory-configurations:


************************************
list-bucket-inventory-configurations
************************************



===========
Description
===========

Returns a list of inventory configurations for the bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/ListBucketInventoryConfigurations>`_


========
Synopsis
========

::

    list-bucket-inventory-configurations
  --bucket <value>
  [--continuation-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
The name of the bucket containing the inventory configurations to retrieve.

``--continuation-token`` (string)
The marker used to continue an inventory configuration listing that has been truncated. Use the NextContinuationToken from a previously truncated list response to continue the listing. The continuation token is an opaque value that Amazon S3 understands.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ContinuationToken -> (string)

  If sent in the request, the marker that is used as a starting point for this inventory configuration list response.

  

InventoryConfigurationList -> (list)

  The list of inventory configurations for a bucket.

  (structure)

    

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

        

      

    

  

IsTruncated -> (boolean)

  Indicates whether the returned list of inventory configurations is truncated in this response. A value of true indicates that the list is truncated.

  

NextContinuationToken -> (string)

  The marker used to continue this inventory configuration listing. Use the NextContinuationToken from this response to continue the listing in a subsequent request. The continuation token is an opaque value that Amazon S3 understands.

  

