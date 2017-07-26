[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch describe-alarms:


***************
describe-alarms
***************



===========
Description
===========



Retrieves alarms with the specified names. If no name is specified, all alarms for the user are returned. Alarms can be retrieved by using only a prefix for the alarm name, the alarm state, or a prefix for any action. 



``describe-alarms`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``MetricAlarms``


========
Synopsis
========

::

    describe-alarms
  [--alarm-names <value>]
  [--alarm-name-prefix <value>]
  [--state-value <value>]
  [--action-prefix <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--alarm-names`` (list)


  A list of alarm names to retrieve information for. 

  



Syntax::

  "string" "string" ...



``--alarm-name-prefix`` (string)


  The alarm name prefix. ``alarm-names`` cannot be specified if this parameter is specified. 

  

``--state-value`` (string)


  The state value to be used in matching alarms. 

  

  Possible values:

  
  *   ``OK``

  
  *   ``ALARM``

  
  *   ``INSUFFICIENT_DATA``

  

  

``--action-prefix`` (string)


  The action name prefix. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list information about an alarm**

The following example uses the ``describe-alarms`` command to provide information about the alarm named "myalarm"::

  aws cloudwatch describe-alarms --alarm-names "myalarm"

Output::

  {
      "MetricAlarms": [
          {
              "EvaluationPeriods": 2,
              "AlarmArn": "arn:aws:cloudwatch:us-east-1:123456789012:alarm:myalarm",
              "StateUpdatedTimestamp": "2014-04-09T18:59:06.442Z",
              "AlarmConfigurationUpdatedTimestamp": "2012-12-27T00:49:54.032Z",
              "ComparisonOperator": "GreaterThanThreshold",
              "AlarmActions": [
                  "arn:aws:sns:us-east-1:123456789012:myHighCpuAlarm"
              ],
              "Namespace": "AWS/EC2",
              "AlarmDescription": "CPU usage exceeds 70 percent",
              "StateReasonData": "{\"version\":\"1.0\",\"queryDate\":\"2014-04-09T18:59:06.419+0000\",\"startDate\":\"2014-04-09T18:44:00.000+0000\",\"statistic\":\"Average\",\"period\":300,\"recentDatapoints\":[38.958,40.292],\"threshold\":70.0}",
              "Period": 300,
              "StateValue": "OK",
              "Threshold": 70.0,
              "AlarmName": "myalarm",
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
              "ActionsEnabled": true,
              "MetricName": "CPUUtilization"
          }
      ]
  }


======
Output
======

MetricAlarms -> (list)

  

  A list of information for the specified alarms. 

  

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

      

      The arithmetic operation to use when comparing the specified ``Statistic`` and ``Threshold`` . The specified ``Statistic`` value is used as the first operand. 

      

      

    

  

NextToken -> (string)

  

  A string that marks the start of the next batch of returned results. 

  

  

