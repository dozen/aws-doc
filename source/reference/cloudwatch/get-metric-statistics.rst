[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch get-metric-statistics:


*********************
get-metric-statistics
*********************



===========
Description
===========



Gets statistics for the specified metric.

 

Amazon CloudWatch retains metric data as follows:

 

 
* Data points with a period of 60 seconds (1-minute) are available for 15 days 
 
* Data points with a period of 300 seconds (5-minute) are available for 63 days 
 
* Data points with a period of 3600 seconds (1 hour) are available for 455 days (15 months) 
 

 

CloudWatch started retaining 5-minute and 1-hour metric data as of July 9, 2016.

 

The maximum number of data points returned from a single call is 1,440. If you request more than 1,440 data points, CloudWatch returns an error. To reduce the number of data points, you can narrow the specified time range and make multiple requests across adjacent time ranges, or you can increase the specified period. A period can be as short as one minute (60 seconds). Data points are not returned in chronological order.

 

CloudWatch aggregates data points based on the length of the period that you specify. For example, if you request statistics with a one-hour period, CloudWatch aggregates all data points with time stamps that fall within each one-hour period. Therefore, the number of values aggregated by CloudWatch is larger than the number of data points returned.

 

CloudWatch needs raw data points to calculate percentile statistics. If you publish data using a statistic set instead, you can only retrieve percentile statistics for this data if one of the following conditions is true:

 

 
* The SampleCount value of the statistic set is 1. 
 
* The Min and the Max values of the statistic set are equal. 
 

 

For a list of metrics and dimensions supported by AWS services, see the `Amazon CloudWatch Metrics and dimensions Reference <http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CW_Support_For_AWS.html>`_ in the *Amazon CloudWatch User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/GetMetricStatistics>`_


========
Synopsis
========

::

    get-metric-statistics
  --namespace <value>
  --metric-name <value>
  [--dimensions <value>]
  --start-time <value>
  --end-time <value>
  --period <value>
  [--statistics <value>]
  [--extended-statistics <value>]
  [--unit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--namespace`` (string)


  The namespace of the metric, with or without spaces.

  

``--metric-name`` (string)


  The name of the metric, with or without spaces.

  

``--dimensions`` (list)


  The dimensions. If the metric contains multiple dimensions, you must include a value for each dimension. CloudWatch treats each unique combination of dimensions as a separate metric. If a specific combination of dimensions was not published, you can't retrieve statistics for it. You must specify the same dimensions that were used when the metrics were created. For an example, see `Dimension Combinations <http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_concepts.html#dimension-combinations>`_ in the *Amazon CloudWatch User Guide* . For more information about specifying dimensions, see `Publishing Metrics <http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/publishingMetrics.html>`_ in the *Amazon CloudWatch User Guide* .

  



Shorthand Syntax::

    Name=string,Value=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string"
    }
    ...
  ]



``--start-time`` (timestamp)


  The time stamp that determines the first data point to return. Start times are evaluated relative to the time that CloudWatch receives the request.

   

  The value specified is inclusive; results include data points with the specified time stamp. The time stamp must be in ISO 8601 UTC format (for example, 2016-10-03T23:00:00Z).

   

  CloudWatch rounds the specified time stamp as follows:

   

   
  * Start time less than 15 days ago - Round down to the nearest whole minute. For example, 12:32:34 is rounded down to 12:32:00. 
   
  * Start time between 15 and 63 days ago - Round down to the nearest 5-minute clock interval. For example, 12:32:34 is rounded down to 12:30:00. 
   
  * Start time greater than 63 days ago - Round down to the nearest 1-hour clock interval. For example, 12:32:34 is rounded down to 12:00:00. 
   

  

``--end-time`` (timestamp)


  The time stamp that determines the last data point to return.

   

  The value specified is exclusive; results include data points up to the specified time stamp. The time stamp must be in ISO 8601 UTC format (for example, 2016-10-10T23:00:00Z).

  

``--period`` (integer)


  The granularity, in seconds, of the returned data points. A period can be as short as one minute (60 seconds) and must be a multiple of 60. 

   

  If the ``StartTime`` parameter specifies a time stamp that is greater than 15 days ago, you must specify the period as follows or no data points in that time range is returned:

   

   
  * Start time between 15 and 63 days ago - Use a multiple of 300 seconds (5 minutes). 
   
  * Start time greater than 63 days ago - Use a multiple of 3600 seconds (1 hour). 
   

  

``--statistics`` (list)


  The metric statistics, other than percentile. For percentile statistics, use ``extended-statistics`` . When calling ``get-metric-statistics`` , you must specify either ``statistics`` or ``extended-statistics`` , but not both.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    SampleCount
    Average
    Sum
    Minimum
    Maximum





``--extended-statistics`` (list)


  The percentile statistics. Specify values between p0.0 and p100. When calling ``get-metric-statistics`` , you must specify either ``statistics`` or ``extended-statistics`` , but not both.

  



Syntax::

  "string" "string" ...



``--unit`` (string)


  The unit for a given metric. Metrics may be reported in multiple units. Not supplying a unit results in all units being returned. If the metric only ever reports one unit, specifying a unit has no effect.

  

  Possible values:

  
  *   ``Seconds``

  
  *   ``Microseconds``

  
  *   ``Milliseconds``

  
  *   ``Bytes``

  
  *   ``Kilobytes``

  
  *   ``Megabytes``

  
  *   ``Gigabytes``

  
  *   ``Terabytes``

  
  *   ``Bits``

  
  *   ``Kilobits``

  
  *   ``Megabits``

  
  *   ``Gigabits``

  
  *   ``Terabits``

  
  *   ``Percent``

  
  *   ``Count``

  
  *   ``Bytes/Second``

  
  *   ``Kilobytes/Second``

  
  *   ``Megabytes/Second``

  
  *   ``Gigabytes/Second``

  
  *   ``Terabytes/Second``

  
  *   ``Bits/Second``

  
  *   ``Kilobits/Second``

  
  *   ``Megabits/Second``

  
  *   ``Gigabits/Second``

  
  *   ``Terabits/Second``

  
  *   ``Count/Second``

  
  *   ``None``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the CPU utilization per EC2 instance**

The following example uses the ``get-metric-statistics`` command to get the CPU utilization for an EC2
instance with the ID i-abcdef. 

.. __: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/US_GetStatistics.html

::

  aws cloudwatch get-metric-statistics --metric-name CPUUtilization --start-time 2014-04-08T23:18:00 --end-time 2014-04-09T23:18:00 --period 3600 --namespace AWS/EC2 --statistics Maximum --dimensions Name=InstanceId,Value=i-abcdef

Output::

    {
        "Datapoints": [
            {
                "Timestamp": "2014-04-09T11:18:00Z",
                "Maximum": 44.79,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T20:18:00Z",
                "Maximum": 47.92,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T19:18:00Z",
                "Maximum": 50.85,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T09:18:00Z",
                "Maximum": 47.92,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T03:18:00Z",
                "Maximum": 76.84,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T21:18:00Z",
                "Maximum": 48.96,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T14:18:00Z",
                "Maximum": 47.92,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T08:18:00Z",
                "Maximum": 47.92,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T16:18:00Z",
                "Maximum": 45.55,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T06:18:00Z",
                "Maximum": 47.92,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T13:18:00Z",
                "Maximum": 45.08,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T05:18:00Z",
                "Maximum": 47.92,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T18:18:00Z",
                "Maximum": 46.88,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T17:18:00Z",
                "Maximum": 52.08,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T07:18:00Z",
                "Maximum": 47.92,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T02:18:00Z",
                "Maximum": 51.23,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T12:18:00Z",
                "Maximum": 47.67,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-08T23:18:00Z",
                "Maximum": 46.88,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T10:18:00Z",
                "Maximum": 51.91,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T04:18:00Z",
                "Maximum": 47.13,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T15:18:00Z",
                "Maximum": 48.96,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T00:18:00Z",
                "Maximum": 48.16,
                "Unit": "Percent"
            },
            {
                "Timestamp": "2014-04-09T01:18:00Z",
                "Maximum": 49.18,
                "Unit": "Percent"
            }
        ],
        "Label": "CPUUtilization"
    }

**Specifying multiple dimensions**

The following example illustrates how to specify multiple dimensions. Each dimension is specified as a Name/Value pair, with a comma between the name and the value. Multiple dimensions are separated by a space. If a single metric includes multiple dimensions, you must specify a value for every defined dimension.

For more examples using the ``get-metric-statistics`` command, see `Get Statistics for a Metric`__ in the *Amazon CloudWatch Developer Guide*.

.. __: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/US_GetStatistics.html

::

  aws cloudwatch get-metric-statistics --metric-name Buffers --namespace MyNameSpace --dimensions Name=InstanceID,Value=i-abcdef Name=InstanceType,Value=m1.small --start-time 2016-10-15T04:00:00Z --end-time 2016-10-19T07:00:00Z --statistics Average --period 60


======
Output
======

Label -> (string)

  

  A label for the specified metric.

  

  

Datapoints -> (list)

  

  The data points for the specified metric.

  

  (structure)

    

    Encapsulates the statistical data that CloudWatch computes from metric data.

    

    Timestamp -> (timestamp)

      

      The time stamp used for the data point.

      

      

    SampleCount -> (double)

      

      The number of metric values that contributed to the aggregate value of this data point.

      

      

    Average -> (double)

      

      The average of the metric values that correspond to the data point.

      

      

    Sum -> (double)

      

      The sum of the metric values for the data point.

      

      

    Minimum -> (double)

      

      The minimum metric value for the data point.

      

      

    Maximum -> (double)

      

      The maximum metric value for the data point.

      

      

    Unit -> (string)

      

      The standard unit for the data point.

      

      

    ExtendedStatistics -> (map)

      

      The percentile statistic for the data point.

      

      key -> (string)

        

        

      value -> (double)

        

        

      

    

  

