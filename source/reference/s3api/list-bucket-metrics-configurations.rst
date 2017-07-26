[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api list-bucket-metrics-configurations:


**********************************
list-bucket-metrics-configurations
**********************************



===========
Description
===========

Lists the metrics configurations for the bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/ListBucketMetricsConfigurations>`_


========
Synopsis
========

::

    list-bucket-metrics-configurations
  --bucket <value>
  [--continuation-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
The name of the bucket containing the metrics configurations to retrieve.

``--continuation-token`` (string)
The marker that is used to continue a metrics configuration listing that has been truncated. Use the NextContinuationToken from a previously truncated list response to continue the listing. The continuation token is an opaque value that Amazon S3 understands.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IsTruncated -> (boolean)

  Indicates whether the returned list of metrics configurations is complete. A value of true indicates that the list is not complete and the NextContinuationToken will be provided for a subsequent request.

  

ContinuationToken -> (string)

  The marker that is used as a starting point for this metrics configuration list response. This value is present if it was sent in the request.

  

NextContinuationToken -> (string)

  The marker used to continue a metrics configuration listing that has been truncated. Use the NextContinuationToken from a previously truncated list response to continue the listing. The continuation token is an opaque value that Amazon S3 understands.

  

MetricsConfigurationList -> (list)

  The list of metrics configurations for a bucket.

  (structure)

    

    Id -> (string)

      The ID used to identify the metrics configuration.

      

    Filter -> (structure)

      Specifies a metrics configuration filter. The metrics configuration will only include objects that meet the filter's criteria. A filter must be a prefix, a tag, or a conjunction (MetricsAndOperator).

      Prefix -> (string)

        The prefix used when evaluating a metrics filter.

        

      Tag -> (structure)

        The tag used when evaluating a metrics filter.

        Key -> (string)

          Name of the tag.

          

        Value -> (string)

          Value of the tag.

          

        

      And -> (structure)

        A conjunction (logical AND) of predicates, which is used in evaluating a metrics filter. The operator must have at least two predicates, and an object must match all of the predicates in order for the filter to apply.

        Prefix -> (string)

          The prefix used when evaluating an AND predicate.

          

        Tags -> (list)

          The list of tags used when evaluating an AND predicate.

          (structure)

            

            Key -> (string)

              Name of the tag.

              

            Value -> (string)

              Value of the tag.

              

            

          

        

      

    

  

