[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs put-metric-filter:


*****************
put-metric-filter
*****************



===========
Description
===========



Creates or updates a metric filter and associates it with the specified log group. Metric filters allow you to configure rules to extract metric data from log events ingested through  put-log-events .

 

The maximum number of metric filters that can be associated with a log group is 100.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/PutMetricFilter>`_


========
Synopsis
========

::

    put-metric-filter
  --log-group-name <value>
  --filter-name <value>
  --filter-pattern <value>
  --metric-transformations <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group.

  

``--filter-name`` (string)


  A name for the metric filter.

  

``--filter-pattern`` (string)


  A filter pattern for extracting metric data out of ingested log events.

  

``--metric-transformations`` (list)


  A collection of information needed to define how metric data gets emitted.

  



Shorthand Syntax::

    metricName=string,metricNamespace=string,metricValue=string,defaultValue=double ...




JSON Syntax::

  [
    {
      "metricName": "string",
      "metricNamespace": "string",
      "metricValue": "string",
      "defaultValue": double
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None