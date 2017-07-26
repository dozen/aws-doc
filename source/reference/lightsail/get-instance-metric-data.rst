[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-instance-metric-data:


************************
get-instance-metric-data
************************



===========
Description
===========



Returns the data points for the specified Amazon Lightsail instance metric, given an instance name.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetInstanceMetricData>`_


========
Synopsis
========

::

    get-instance-metric-data
  --instance-name <value>
  --metric-name <value>
  --period <value>
  --start-time <value>
  --end-time <value>
  --unit <value>
  --statistics <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-name`` (string)


  The name of the instance for which you want to get metrics data.

  

``--metric-name`` (string)


  The metric name to get data about. 

  

  Possible values:

  
  *   ``CPUUtilization``

  
  *   ``NetworkIn``

  
  *   ``NetworkOut``

  
  *   ``StatusCheckFailed``

  
  *   ``StatusCheckFailed_Instance``

  
  *   ``StatusCheckFailed_System``

  

  

``--period`` (integer)


  The time period for which you are requesting data.

  

``--start-time`` (timestamp)


  The start time of the time period.

  

``--end-time`` (timestamp)


  The end time of the time period.

  

``--unit`` (string)


  The unit. The list of valid values is below.

  

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

  

  

``--statistics`` (list)


  The instance statistics. 

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Minimum
    Maximum
    Sum
    Average
    SampleCount





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

metricName -> (string)

  

  The metric name to return data for. 

  

  

metricData -> (list)

  

  An array of key-value pairs containing information about the results of your get instance metric data request.

  

  (structure)

    

    Describes the metric data point.

    

    average -> (double)

      

      The average.

      

      

    maximum -> (double)

      

      The maximum.

      

      

    minimum -> (double)

      

      The minimum.

      

      

    sampleCount -> (double)

      

      The sample count.

      

      

    sum -> (double)

      

      The sum.

      

      

    timestamp -> (timestamp)

      

      The start-time (e.g., ``1479816991.349`` ).

      

      

    unit -> (string)

      

      The unit. 

      

      

    

  

