[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs put-metric-filter:


*****************
put-metric-filter
*****************



===========
Description
===========



Creates or updates a metric filter and associates it with the specified log group. Metric filters allow you to configure rules to extract metric data from log events ingested through ``put-log-events`` requests. 

 

The maximum number of metric filters that can be associated with a log group is 100. 



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
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group to associate the metric filter with.

  

``--filter-name`` (string)


  A name for the metric filter.

  

``--filter-pattern`` (string)


  A valid CloudWatch Logs filter pattern for extracting metric data out of ingested log events.

  

``--metric-transformations`` (list)


  A collection of information needed to define how metric data gets emitted.

  



Shorthand Syntax::

    metricName=string,metricNamespace=string,metricValue=string ...




JSON Syntax::

  [
    {
      "metricName": "string",
      "metricNamespace": "string",
      "metricValue": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None