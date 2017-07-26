[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch describe-alarms-for-metric:


**************************
describe-alarms-for-metric
**************************



===========
Description
===========



Retrieves all alarms for a single metric. Specify a statistic, period, or unit to filter the set of alarms further. 



========
Synopsis
========

::

    describe-alarms-for-metric
  --metric-name <value>
  --namespace <value>
  [--statistic <value>]
  [--dimensions <value>]
  [--period <value>]
  [--unit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--metric-name`` (string)


  The name of the metric. 

  

``--namespace`` (string)


  The namespace of the metric. 

  

``--statistic`` (string)


  The statistic for the metric. 

  

  Possible values:

  
  *   ``SampleCount``

  
  *   ``Average``

  
  *   ``Sum``

  
  *   ``Minimum``

  
  *   ``Maximum``

  

  

``--dimensions`` (list)


  The list of dimensions associated with the metric. If the metric has any associated dimensions, you must specify them in order for the describe-alarms-for-metric to succeed. 

  



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



``--period`` (integer)


  The period in seconds over which the statistic is applied. 

  

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

**To display information about alarms associated with a metric**

The following example uses the ``describe-alarms-for-metric`` command to display information about
any alarms associated with the Amazon EC2 CPUUtilization metric and the instance with the ID i-0c986c72.::

  aws cloudwatch describe-alarms-for-metric --metric-name CPUUtilization --namespace AWS/EC2 --dimensions Name=InstanceId,Value=i-0c986c72

Output::

  {
      "MetricAlarms": [
          {
              "EvaluationPeriods": 10,
              "AlarmArn": "arn:aws:cloudwatch:us-east-1:111122223333:alarm:myHighCpuAlarm2",
              "StateUpdatedTimestamp": "2013-10-30T03:03:51.479Z",
              "AlarmConfigurationUpdatedTimestamp": "2013-10-30T03:03:50.865Z",
              "ComparisonOperator": "GreaterThanOrEqualToThreshold",
              "AlarmActions": [
                  "arn:aws:sns:us-east-1:111122223333:NotifyMe"
              ],
              "Namespace": "AWS/EC2",
              "AlarmDescription": "CPU usage exceeds 70 percent",
              "StateReasonData": "{\"version\":\"1.0\",\"queryDate\":\"2013-10-30T03:03:51.479+0000\",\"startDate\":\"2013-10-30T02:08:00.000+0000\",\"statistic\":\"Average\",\"period\":300,\"recentDatapoints\":[40.698,39.612,42.432,39.796,38.816,42.28,42.854,40.088,40.760000000000005,41.316],\"threshold\":70.0}",
              "Period": 300,
              "StateValue": "OK",
              "Threshold": 70.0,
              "AlarmName": "myHighCpuAlarm2",
              "Dimensions": [
                  {
                      "Name": "InstanceId",
                      "Value": "i-0c986c72"
                  }
              ],
              "Statistic": "Average",
              "StateReason": "Threshold Crossed: 10 datapoints were not greater than or equal to the threshold (70.0). The most recent datapoints: [40.760000000000005, 41.316].",
              "InsufficientDataActions": [],
              "OKActions": [],
              "ActionsEnabled": true,
              "MetricName": "CPUUtilization"
          },
          {
              "EvaluationPeriods": 2,
              "AlarmArn": "arn:aws:cloudwatch:us-east-1:111122223333:alarm:myHighCpuAlarm",
              "StateUpdatedTimestamp": "2014-04-09T18:59:06.442Z",
              "AlarmConfigurationUpdatedTimestamp": "2014-04-09T22:26:05.958Z",
              "ComparisonOperator": "GreaterThanThreshold",
              "AlarmActions": [
                  "arn:aws:sns:us-east-1:111122223333:HighCPUAlarm"
              ],
              "Namespace": "AWS/EC2",
              "AlarmDescription": "CPU usage exceeds 70 percent",
              "StateReasonData": "{\"version\":\"1.0\",\"queryDate\":\"2014-04-09T18:59:06.419+0000\",\"startDate\":\"2014-04-09T18:44:00.000+0000\",\"statistic\":\"Average\",\"period\":300,\"recentDatapoints\":[38.958,40.292],\"threshold\":70.0}",
              "Period": 300,
              "StateValue": "OK",
              "Threshold": 70.0,
              "AlarmName": "myHighCpuAlarm",
              "Dimensions": [
                  {
                      "Name": "InstanceId",
                      "Value": "i-0c986c72"
                  }
              ],
              "Statistic": "Average",
              "StateReason": "Threshold Crossed: 2 datapoints were not greater than the threshold (70.0). The most recent datapoints: [38.958, 40.292].",
              "InsufficientDataActions": [],
              "OKActions": [],
              "ActionsEnabled": false,
              "MetricName": "CPUUtilization"
          }
      ]
  }



======
Output
======

MetricAlarms -> (list)

  

  A list of information for each alarm with the specified metric. 

  

  (structure)

    

    The  MetricAlarm data type represents an alarm. You can use  put-metric-alarm to create or update an alarm. 

    

    AlarmName -> (string)

      

      The name of the alarm. 

      

      

    AlarmArn -> (string)

      

      The Amazon Resource Name (ARN) of the alarm. 

      

      

    AlarmDescription -> (string)

      

      The description for the alarm. 

      

      

    AlarmConfigurationUpdatedTimestamp -> (timestamp)

      

      The time stamp of the last update to the alarm configuration. 

      

      

    ActionsEnabled -> (boolean)

      

      Indicates whether actions should be executed during any changes to the alarm's state. 

      

      

    OKActions -> (list)

      

      The list of actions to execute when this alarm transitions into an ``OK`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

      

      (string)

        

        

      

    AlarmActions -> (list)

      

      The list of actions to execute when this alarm transitions into an ``ALARM`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

      

      (string)

        

        

      

    InsufficientDataActions -> (list)

      

      The list of actions to execute when this alarm transitions into an ``INSUFFICIENT_DATA`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

       

      .. warning::

        The current WSDL lists this attribute as ``UnknownActions`` .

      

      (string)

        

        

      

    StateValue -> (string)

      

      The state value for the alarm. 

      

      

    StateReason -> (string)

      

      A human-readable explanation for the alarm's state. 

      

      

    StateReasonData -> (string)

      

      An explanation for the alarm's state in machine-readable JSON format 

      

      

    StateUpdatedTimestamp -> (timestamp)

      

      The time stamp of the last update to the alarm's state. 

      

      

    MetricName -> (string)

      

      The name of the alarm's metric. 

      

      

    Namespace -> (string)

      

      The namespace of alarm's associated metric. 

      

      

    Statistic -> (string)

      

      The statistic to apply to the alarm's associated metric. 

      

      

    Dimensions -> (list)

      

      The list of dimensions associated with the alarm's associated metric. 

      

      (structure)

        

        The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

         

        For examples that use one or more dimensions, see  put-metric-data .

        

        Name -> (string)

          

          The name of the dimension. 

          

          

        Value -> (string)

          

          The value representing the dimension measurement 

          

          

        

      

    Period -> (integer)

      

      The period in seconds over which the statistic is applied. 

      

      

    Unit -> (string)

      

      The unit of the alarm's associated metric. 

      

      

    EvaluationPeriods -> (integer)

      

      The number of periods over which data is compared to the specified threshold. 

      

      

    Threshold -> (double)

      

      The value against which the specified statistic is compared. 

      

      

    ComparisonOperator -> (string)

      

      The arithmetic operation to use when comparing the specified ``statistic`` and ``Threshold`` . The specified ``statistic`` value is used as the first operand. 

      

      

    

  

