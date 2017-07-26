[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch put-metric-data:


***************
put-metric-data
***************



===========
Description
===========



Publishes metric data points to Amazon CloudWatch. Amazon CloudWatch associates the data points with the specified metric. If the specified metric does not exist, Amazon CloudWatch creates the metric. When Amazon CloudWatch creates a metric, it can take up to fifteen minutes for the metric to appear in calls to the  list-metrics action. 

 

Each ``put-metric-data`` request is limited to 8 KB in size for HTTP GET requests and is limited to 40 KB in size for HTTP POST requests. 

 

.. warning::

  Although the ``Value`` parameter accepts numbers of type ``Double`` , Amazon CloudWatch rejects values that are either too small or too large. Values must be in the range of 8.515920e-109 to 1.174271e+108 (Base 10) or 2e-360 to 2e360 (Base 2). In addition, special values (e.g., NaN, +Infinity, -Infinity) are not supported. 

 

Data that is timestamped 24 hours or more in the past may take in excess of 48 hours to become available from submission time using ``get-metric-statistics`` .



========
Synopsis
========

::

    put-metric-data
  --namespace <value>
  [--metric-data <value>]
  [--metric-name <value>]
  [--timestamp <value>]
  [--unit <value>]
  [--value <value>]
  [--dimensions <value>]
  [--statistic-values <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--namespace`` (string)


  The namespace for the metric data. 

   

  .. note::

    You cannot specify a namespace that begins with "AWS/". Namespaces that begin with "AWS/" are reserved for other Amazon Web Services products that send metrics to Amazon CloudWatch. 

  

``--metric-data`` (list)


  A list of data describing the metric. 

  



Shorthand Syntax::

    MetricName=string,Dimensions=[{Name=string,Value=string},{Name=string,Value=string}],Timestamp=timestamp,Value=double,StatisticValues={SampleCount=double,Sum=double,Minimum=double,Maximum=double},Unit=string ...




JSON Syntax::

  [
    {
      "MetricName": "string",
      "Dimensions": [
        {
          "Name": "string",
          "Value": "string"
        }
        ...
      ],
      "Timestamp": timestamp,
      "Value": double,
      "StatisticValues": {
        "SampleCount": double,
        "Sum": double,
        "Minimum": double,
        "Maximum": double
      },
      "Unit": "Seconds"|"Microseconds"|"Milliseconds"|"Bytes"|"Kilobytes"|"Megabytes"|"Gigabytes"|"Terabytes"|"Bits"|"Kilobits"|"Megabits"|"Gigabits"|"Terabits"|"Percent"|"Count"|"Bytes/Second"|"Kilobytes/Second"|"Megabytes/Second"|"Gigabytes/Second"|"Terabytes/Second"|"Bits/Second"|"Kilobits/Second"|"Megabits/Second"|"Gigabits/Second"|"Terabits/Second"|"Count/Second"|"None"
    }
    ...
  ]



``--metric-name`` (string)
The name of the metric.

``--timestamp`` (string)
The time stamp used for the metric. If not specified, the default value is set to the time the metric data was received.

``--unit`` (string)
The unit of metric.

``--value`` (string)
The value for the metric. Although the --value parameter accepts numbers of type Double, Amazon CloudWatch truncates values with very large exponents. Values with base-10 exponents greater than 126 (1 x 10^126) are truncated. Likewise, values with base-10 exponents less than -130 (1 x 10^-130) are also truncated.

``--dimensions`` (string)
The --dimension argument further expands on the identity of a metric using a Name=Valuepair, separated by commas, for example: ``--dimensions User=SomeUser,Stack=Test`` 

``--statistic-values`` (string)
A set of statistical values describing the metric.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To publish a custom metric to Amazon CloudWatch**

The following example uses the ``put-metric-data`` command to publish a custom metric to Amazon CloudWatch::

  aws cloudwatch put-metric-data --namespace "Usage Metrics" --metric-data file://metric.json

The values for the metric itself are stored in the JSON file, ``metric.json``.

Here are the contents of that file::

  [
    {
      "MetricName": "New Posts",
      "Timestamp": "Wednesday, June 12, 2013 8:28:20 PM",
      "Value": 0.50,
      "Unit": "Count"
    }
  ]

For more information, see `Publishing Custom Metrics`_ in the *Amazon CloudWatch Developer Guide*.

.. _`Publishing Custom Metrics`: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/publishingMetrics.html




======
Output
======

None