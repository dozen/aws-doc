[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch put-metric-data:


***************
put-metric-data
***************



===========
Description
===========



Publishes metric data points to Amazon CloudWatch. CloudWatch associates the data points with the specified metric. If the specified metric does not exist, CloudWatch creates the metric. When CloudWatch creates a metric, it can take up to fifteen minutes for the metric to appear in calls to  list-metrics .

 

Each ``put-metric-data`` request is limited to 40 KB in size for HTTP POST requests.

 

Although the ``Value`` parameter accepts numbers of type ``Double`` , CloudWatch rejects values that are either too small or too large. Values must be in the range of 8.515920e-109 to 1.174271e+108 (Base 10) or 2e-360 to 2e360 (Base 2). In addition, special values (for example, NaN, +Infinity, -Infinity) are not supported.

 

You can use up to 10 dimensions per metric to further clarify what data the metric collects. For more information about specifying dimensions, see `Publishing Metrics <http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/publishingMetrics.html>`_ in the *Amazon CloudWatch User Guide* .

 

Data points with time stamps from 24 hours ago or longer can take at least 48 hours to become available for  get-metric-statistics from the time they are submitted.

 

CloudWatch needs raw data points to calculate percentile statistics. If you publish data using a statistic set instead, you can only retrieve percentile statistics for this data if one of the following conditions is true:

 

 
* The SampleCount value of the statistic set is 1 
 
* The Min and the Max values of the statistic set are equal 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/PutMetricData>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--namespace`` (string)


  The namespace for the metric data.

   

  You cannot specify a namespace that begins with "AWS/". Namespaces that begin with "AWS/" are reserved for use by Amazon Web Services products.

  

``--metric-data`` (list)


  The data for the metric.

  



Shorthand Syntax::

    MetricName=string,Dimensions=[{Name=string,Value=string},{Name=string,Value=string}],Timestamp=timestamp,Value=double,StatisticValues={SampleCount=double,Sum=double,Minimum=double,Maximum=double},Unit=string,StorageResolution=integer ...




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
      "Unit": "Seconds"|"Microseconds"|"Milliseconds"|"Bytes"|"Kilobytes"|"Megabytes"|"Gigabytes"|"Terabytes"|"Bits"|"Kilobits"|"Megabits"|"Gigabits"|"Terabits"|"Percent"|"Count"|"Bytes/Second"|"Kilobytes/Second"|"Megabytes/Second"|"Gigabytes/Second"|"Terabytes/Second"|"Bits/Second"|"Kilobits/Second"|"Megabits/Second"|"Gigabits/Second"|"Terabits/Second"|"Count/Second"|"None",
      "StorageResolution": integer
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
The --dimensions argument further expands on the identity of a metric using a Name=Value pair, separated by commas, for example: ``--dimensions InstanceID=1-23456789 InstanceType=m1.small`` . Note that the ``--dimensions`` argument has a different format when used in ``get-metric-data`` , where for the same example you would use the format ``--dimensions Name=InstanceID,Value=i-aaba32d4 Name=InstanceType,value=m1.small`` .

``--statistic-values`` (string)
A set of statistical values describing the metric.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

**To specify multiple dimensions**

The following example illustrates how to specify multiple dimensions. Each dimension is specified as a Name=Value pair. Multiple dimensions are separated by a comma.::

  aws cloudwatch put-metric-data --metric-name Buffers --namespace MyNameSpace --unit Bytes --value 231434333 --dimensions InstanceID=1-23456789,InstanceType=m1.small


======
Output
======

None