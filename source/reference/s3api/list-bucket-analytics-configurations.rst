[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api list-bucket-analytics-configurations:


************************************
list-bucket-analytics-configurations
************************************



===========
Description
===========

Lists the analytics configurations for the bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/ListBucketAnalyticsConfigurations>`_


========
Synopsis
========

::

    list-bucket-analytics-configurations
  --bucket <value>
  [--continuation-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
The name of the bucket from which analytics configurations are retrieved.

``--continuation-token`` (string)
The ContinuationToken that represents a placeholder from where this request should begin.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IsTruncated -> (boolean)

  Indicates whether the returned list of analytics configurations is complete. A value of true indicates that the list is not complete and the NextContinuationToken will be provided for a subsequent request.

  

ContinuationToken -> (string)

  The ContinuationToken that represents where this request began.

  

NextContinuationToken -> (string)

  NextContinuationToken is sent when isTruncated is true, which indicates that there are more analytics configurations to list. The next request must include this NextContinuationToken. The token is obfuscated and is not a usable value.

  

AnalyticsConfigurationList -> (list)

  The list of analytics configurations for a bucket.

  (structure)

    

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

              

            

          

        

      

    

  

