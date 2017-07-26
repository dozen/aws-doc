[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs describe-metric-filters:


***********************
describe-metric-filters
***********************



===========
Description
===========



Lists the specified metric filters. You can list all the metric filters or filter the results by log name, prefix, metric name, and metric namespace. The results are ASCII-sorted by filter name.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/DescribeMetricFilters>`_


``describe-metric-filters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``metricFilters``


========
Synopsis
========

::

    describe-metric-filters
  [--log-group-name <value>]
  [--filter-name-prefix <value>]
  [--metric-name <value>]
  [--metric-namespace <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group.

  

``--filter-name-prefix`` (string)


  The prefix to match.

  

``--metric-name`` (string)


  The name of the CloudWatch metric.

  

``--metric-namespace`` (string)


  The namespace of the CloudWatch metric.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

metricFilters -> (list)

  

  The metric filters.

  

  (structure)

    

    Metric filters express how CloudWatch Logs would extract metric observations from ingested log events and transform them into metric data in a CloudWatch metric.

    

    filterName -> (string)

      

      The name of the metric filter.

      

      

    filterPattern -> (string)

      

      A symbolic description of how CloudWatch Logs should interpret the data in each log event. For example, a log event may contain timestamps, IP addresses, strings, and so on. You use the filter pattern to specify what to look for in the log event message.

      

      

    metricTransformations -> (list)

      

      The metric transformations.

      

      (structure)

        

        Indicates how to transform ingested log events into metric data in a CloudWatch metric.

        

        metricName -> (string)

          

          The name of the CloudWatch metric.

          

          

        metricNamespace -> (string)

          

          The namespace of the CloudWatch metric.

          

          

        metricValue -> (string)

          

          The value to publish to the CloudWatch metric when a filter pattern matches a log event.

          

          

        defaultValue -> (double)

          

          (Optional) The value to emit when a filter pattern does not match a log event. This value can be null.

          

          

        

      

    creationTime -> (long)

      

      The creation time of the metric filter, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    logGroupName -> (string)

      

      The name of the log group.

      

      

    

  

nextToken -> (string)

  

  The token for the next set of items to return. The token expires after 24 hours.

  

  

