[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch get-metric-statistics:


*********************
get-metric-statistics
*********************



===========
Description
===========



Gets statistics for the specified metric. 

 

The maximum number of data points that can be queried is 50,850, whereas the maximum number of data points returned from a single ``get-metric-statistics`` request is 1,440. If you make a request that generates more than 1,440 data points, Amazon CloudWatch returns an error. In such a case, you can alter the request by narrowing the specified time range or increasing the specified period. Alternatively, you can make multiple requests across adjacent time ranges. ``get-metric-statistics`` does not return the data in chronological order. 

 

Amazon CloudWatch aggregates data points based on the length of the ``period`` that you specify. For example, if you request statistics with a one-minute granularity, Amazon CloudWatch aggregates data points with time stamps that fall within the same one-minute period. In such a case, the data points queried can greatly outnumber the data points returned. 

 

The following examples show various statistics allowed by the data point query maximum of 50,850 when you call ``get-metric-statistics`` on Amazon EC2 instances with detailed (one-minute) monitoring enabled: 

 

 
* statistics for up to 400 instances for a span of one hour
 
* statistics for up to 35 instances over a span of 24 hours
 
* statistics for up to 2 instances over a span of 2 weeks
 

 

For information about the namespace, metric names, and dimensions that other Amazon Web Services products use to send metrics to CloudWatch, go to `Amazon CloudWatch Metrics, Namespaces, and dimensions Reference`_ in the *Amazon CloudWatch Developer Guide* . 



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
  --statistics <value>
  [--unit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--namespace`` (string)


  The namespace of the metric, with or without spaces. 

  

``--metric-name`` (string)


  The name of the metric, with or without spaces. 

  

``--dimensions`` (list)


  A list of dimensions describing qualities of the metric. 

  



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


  The time stamp to use for determining the first datapoint to return. The value specified is inclusive; results include datapoints with the time stamp specified. The time stamp must be in ISO 8601 UTC format (e.g., 2014-09-03T23:00:00Z). 

   

  .. note::

    The specified start time is rounded down to the nearest value. Datapoints are returned for start times up to two weeks in the past. Specified start times that are more than two weeks in the past will not return datapoints for metrics that are older than two weeks. 

    Data that is timestamped 24 hours or more in the past may take in excess of 48 hours to become available from submission time using ``get-metric-statistics`` .

     

  

``--end-time`` (timestamp)


  The time stamp to use for determining the last datapoint to return. The value specified is exclusive; results will include datapoints up to the time stamp specified. The time stamp must be in ISO 8601 UTC format (e.g., 2014-09-03T23:00:00Z). 

  

``--period`` (integer)


  The granularity, in seconds, of the returned datapoints. ``period`` must be at least 60 seconds and must be a multiple of 60. The default value is 60. 

  

``--statistics`` (list)


  The metric statistics to return. For information about specific statistics returned by GetMetricStatistics, see `statistics`_ in the *Amazon CloudWatch Developer Guide* . 

  



Syntax::

  "string" "string" ...

  Where valid values are:
    SampleCount
    Average
    Sum
    Minimum
    Maximum





``--unit`` (string)


  The unit for the metric. 

  

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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get the CPU utilization per EC2 instance**

The following example uses the ``get-metric-statistics`` command to get the CPU utilization for an EC2
instance with the ID i-abcdef. For more examples using the ``get-metric-statistics`` command, see `Get Statistics for a Metric`__ in the *Amazon CloudWatch Developer Guide*.

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



======
Output
======

Label -> (string)

  

  A label describing the specified metric. 

  

  

Datapoints -> (list)

  

  The datapoints for the specified metric. 

  

  (structure)

    

    The ``Datapoint`` data type encapsulates the statistical data that Amazon CloudWatch computes from metric data. 

    

    Timestamp -> (timestamp)

      

      The time stamp used for the datapoint. 

      

      

    SampleCount -> (double)

      

      The number of metric values that contributed to the aggregate value of this datapoint. 

      

      

    Average -> (double)

      

      The average of metric values that correspond to the datapoint. 

      

      

    Sum -> (double)

      

      The sum of metric values used for the datapoint. 

      

      

    Minimum -> (double)

      

      The minimum metric value used for the datapoint. 

      

      

    Maximum -> (double)

      

      The maximum of the metric value used for the datapoint. 

      

      

    Unit -> (string)

      

      The standard unit used for the datapoint. 

      

      

    

  



.. _Amazon CloudWatch Metrics, Namespaces, and dimensions Reference: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html
.. _statistics: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#Statistic
