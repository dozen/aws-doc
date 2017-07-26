[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-analytics-configuration:


**********************************
get-bucket-analytics-configuration
**********************************



===========
Description
===========

Gets an analytics configuration for the bucket (specified by the analytics configuration ID).

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetBucketAnalyticsConfiguration>`_


========
Synopsis
========

::

    get-bucket-analytics-configuration
  --bucket <value>
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
The name of the bucket from which an analytics configuration is retrieved.

``--id`` (string)
The identifier used to represent an analytics configuration.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AnalyticsConfiguration -> (structure)

  The configuration and any analyses for the analytics filter.

  Id -> (string)

    The identifier used to represent an analytics configuration.

    

  Filter -> (structure)

    The filter used to describe a set of objects for analyses. A filter must have exactly one prefix, one tag, or one conjunction (AnalyticsAndOperator). If no filter is provided, all objects will be considered in any analysis.

    Prefix -> (string)

      The prefix to use when evaluating an analytics filter.

      

    Tag -> (structure)

      The tag to use when evaluating an analytics filter.

      Key -> (string)

        Name of the tag.

        

      Value -> (string)

        Value of the tag.

        

      

    And -> (structure)

      A conjunction (logical AND) of predicates, which is used in evaluating an analytics filter. The operator must have at least two predicates.

      Prefix -> (string)

        The prefix to use when evaluating an AND predicate.

        

      Tags -> (list)

        The list of tags to use when evaluating an AND predicate.

        (structure)

          

          Key -> (string)

            Name of the tag.

            

          Value -> (string)

            Value of the tag.

            

          

        

      

    

  StorageClassAnalysis -> (structure)

    If present, it indicates that data related to access patterns will be collected and made available to analyze the tradeoffs between different storage classes.

    DataExport -> (structure)

      A container used to describe how data related to the storage class analysis should be exported.

      OutputSchemaVersion -> (string)

        The version of the output schema to use when exporting data. Must be V_1.

        

      Destination -> (structure)

        The place to store the data for an analysis.

        S3BucketDestination -> (structure)

          A destination signifying output to an S3 bucket.

          Format -> (string)

            The file format used when exporting data to Amazon S3.

            

          BucketAccountId -> (string)

            The account ID that owns the destination bucket. If no account ID is provided, the owner will not be validated prior to exporting data.

            

          Bucket -> (string)

            The Amazon resource name (ARN) of the bucket to which data is exported.

            

          Prefix -> (string)

            The prefix to use when exporting data. The exported data begins with this prefix.

            

          

        

      

    

  

