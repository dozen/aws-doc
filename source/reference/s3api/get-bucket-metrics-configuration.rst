[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-metrics-configuration:


********************************
get-bucket-metrics-configuration
********************************



===========
Description
===========

Gets a metrics configuration (specified by the metrics configuration ID) from the bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetBucketMetricsConfiguration>`_


========
Synopsis
========

::

    get-bucket-metrics-configuration
  --bucket <value>
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
The name of the bucket containing the metrics configuration to retrieve.

``--id`` (string)
The ID used to identify the metrics configuration.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MetricsConfiguration -> (structure)

  Specifies the metrics configuration.

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

            

          

        

      

    

  

