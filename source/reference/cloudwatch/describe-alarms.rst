[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch describe-alarms:


***************
describe-alarms
***************



===========
Description
===========



Retrieves the specified alarms. If no alarms are specified, all alarms are returned. Alarms can be retrieved by using only a prefix for the alarm name, the alarm state, or a prefix for any action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/DescribeAlarms>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--alarm-names`` (list)


  The names of the alarms.

  



Syntax::

  "string" "string" ...



``--alarm-name-prefix`` (string)


  The alarm name prefix. If this parameter is specified, you cannot specify ``alarm-names`` .

  

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

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  The information for the specified alarms.

  

  (structure)

    

    Represents an alarm.

    

    AlarmName -> (string)

      

      The name of the alarm.

      

      

    AlarmArn -> (string)

      

      The Amazon Resource Name (ARN) of the alarm.

      

      

    AlarmDescription -> (string)

      

      The description of the alarm.

      

      

    AlarmConfigurationUpdatedTimestamp -> (timestamp)

      

      The time stamp of the last update to the alarm configuration.

      

      

    ActionsEnabled -> (boolean)

      

      Indicates whether actions should be executed during any changes to the alarm state.

      

      

    OKActions -> (list)

      

      The actions to execute when this alarm transitions to the ``OK`` state from any other state. Each action is specified as an Amazon Resource Name (ARN).

      

      (string)

        

        

      

    AlarmActions -> (list)

      

      The actions to execute when this alarm transitions to the ``ALARM`` state from any other state. Each action is specified as an Amazon Resource Name (ARN).

      

      (string)

        

        

      

    InsufficientDataActions -> (list)

      

      The actions to execute when this alarm transitions to the ``INSUFFICIENT_DATA`` state from any other state. Each action is specified as an Amazon Resource Name (ARN).

      

      (string)

        

        

      

    StateValue -> (string)

      

      The state value for the alarm.

      

      

    StateReason -> (string)

      

      An explanation for the alarm state, in text format.

      

      

    StateReasonData -> (string)

      

      An explanation for the alarm state, in JSON format.

      

      

    StateUpdatedTimestamp -> (timestamp)

      

      The time stamp of the last update to the alarm state.

      

      

    MetricName -> (string)

      

      The name of the metric associated with the alarm.

      

      

    Namespace -> (string)

      

      The namespace of the metric associated with the alarm.

      

      

    Statistic -> (string)

      

      The statistic for the metric associated with the alarm, other than percentile. For percentile statistics, use ``ExtendedStatistic`` .

      

      

    ExtendedStatistic -> (string)

      

      The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.

      

      

    Dimensions -> (list)

      

      The dimensions for the metric associated with the alarm.

      

      (structure)

        

        Expands the identity of a metric.

        

        Name -> (string)

          

          The name of the dimension.

          

          

        Value -> (string)

          

          The value representing the dimension measurement.

          

          

        

      

    Period -> (integer)

      

      The period, in seconds, over which the statistic is applied.

      

      

    Unit -> (string)

      

      The unit of the metric associated with the alarm.

      

      

    EvaluationPeriods -> (integer)

      

      The number of periods over which data is compared to the specified threshold.

      

      

    Threshold -> (double)

      

      The value to compare with the specified statistic.

      

      

    ComparisonOperator -> (string)

      

      The arithmetic operation to use when comparing the specified statistic and threshold. The specified statistic value is used as the first operand.

      

      

    TreatMissingData -> (string)

      

      Sets how this alarm is to handle missing data points. If this parameter is omitted, the default behavior of ``missing`` is used.

      

      

    EvaluateLowSampleCountPercentile -> (string)

      

      Used only for alarms based on percentiles. If ``ignore`` , the alarm state does not change during periods with too few data points to be statistically significant. If ``evaluate`` or this parameter is not used, the alarm will always be evaluated and possibly change state no matter how many data points are available.

      

      

    

  

NextToken -> (string)

  

  The token that marks the start of the next batch of returned results.

  

  

