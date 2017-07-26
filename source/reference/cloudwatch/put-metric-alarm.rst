[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch put-metric-alarm:


****************
put-metric-alarm
****************



===========
Description
===========



Creates or updates an alarm and associates it with the specified metric. Optionally, this operation can associate one or more Amazon SNS resources with the alarm.

 

When this operation creates an alarm, the alarm state is immediately set to ``INSUFFICIENT_DATA`` . The alarm is evaluated and its state is set appropriately. Any actions associated with the state are then executed.

 

When you update an existing alarm, its state is left unchanged, but the update completely overwrites the previous configuration of the alarm.

 

If you are an IAM user, you must have Amazon EC2 permissions for some operations:

 

 
* ``ec2:DescribeInstanceStatus`` and ``ec2:DescribeInstances`` for all alarms on EC2 instance status metrics 
 
* ``ec2:StopInstances`` for alarms with stop actions 
 
* ``ec2:TerminateInstances`` for alarms with terminate actions 
 
* ``ec2:DescribeInstanceRecoveryAttribute`` and ``ec2:RecoverInstances`` for alarms with recover actions 
 

 

If you have read/write permissions for Amazon CloudWatch but not for Amazon EC2, you can still create an alarm, but the stop or terminate actions are not performed. However, if you are later granted the required permissions, the alarm actions that you created earlier are performed.

 

If you are using an IAM role (for example, an EC2 instance profile), you cannot stop or terminate the instance using alarm actions. However, you can still see the alarm state and perform any other actions such as Amazon SNS notifications or Auto Scaling policies.

 

If you are using temporary security credentials granted using AWS STS, you cannot stop or terminate an EC2 instance using alarm actions.

 

You must create at least one stop, terminate, or reboot alarm using either the Amazon EC2 or CloudWatch consoles to create the **EC2ActionsAccess** IAM role. After this IAM role is created, you can create stop, terminate, or reboot alarms using a command-line interface or API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/PutMetricAlarm>`_


========
Synopsis
========

::

    put-metric-alarm
  --alarm-name <value>
  [--alarm-description <value>]
  [--actions-enabled | --no-actions-enabled]
  [--ok-actions <value>]
  [--alarm-actions <value>]
  [--insufficient-data-actions <value>]
  --metric-name <value>
  --namespace <value>
  [--statistic <value>]
  [--extended-statistic <value>]
  [--dimensions <value>]
  --period <value>
  [--unit <value>]
  --evaluation-periods <value>
  --threshold <value>
  --comparison-operator <value>
  [--treat-missing-data <value>]
  [--evaluate-low-sample-count-percentile <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--alarm-name`` (string)


  The name for the alarm. This name must be unique within the AWS account.

  

``--alarm-description`` (string)


  The description for the alarm.

  

``--actions-enabled`` | ``--no-actions-enabled`` (boolean)


  Indicates whether actions should be executed during any changes to the alarm state.

  

``--ok-actions`` (list)


  The actions to execute when this alarm transitions to an ``OK`` state from any other state. Each action is specified as an Amazon Resource Name (ARN).

   

  Valid Values: arn:aws:automate:*region* :ec2:stop | arn:aws:automate:*region* :ec2:terminate | arn:aws:automate:*region* :ec2:recover

   

  Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

  



Syntax::

  "string" "string" ...



``--alarm-actions`` (list)


  The actions to execute when this alarm transitions to the ``ALARM`` state from any other state. Each action is specified as an Amazon Resource Name (ARN).

   

  Valid Values: arn:aws:automate:*region* :ec2:stop | arn:aws:automate:*region* :ec2:terminate | arn:aws:automate:*region* :ec2:recover

   

  Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

  



Syntax::

  "string" "string" ...



``--insufficient-data-actions`` (list)


  The actions to execute when this alarm transitions to the ``INSUFFICIENT_DATA`` state from any other state. Each action is specified as an Amazon Resource Name (ARN).

   

  Valid Values: arn:aws:automate:*region* :ec2:stop | arn:aws:automate:*region* :ec2:terminate | arn:aws:automate:*region* :ec2:recover

   

  Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

  



Syntax::

  "string" "string" ...



``--metric-name`` (string)


  The name for the metric associated with the alarm.

  

``--namespace`` (string)


  The namespace for the metric associated with the alarm.

  

``--statistic`` (string)


  The statistic for the metric associated with the alarm, other than percentile. For percentile statistics, use ``extended-statistic`` .

  

  Possible values:

  
  *   ``SampleCount``

  
  *   ``Average``

  
  *   ``Sum``

  
  *   ``Minimum``

  
  *   ``Maximum``

  

  

``--extended-statistic`` (string)


  The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.

  

``--dimensions`` (list)


  The dimensions for the metric associated with the alarm.

  



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


  The period, in seconds, over which the specified statistic is applied. An alarm's total current evaluation period can be no longer than one day, so this number multiplied by ``evaluation-periods`` must be 86,400 or less.

  

``--unit`` (string)


  The unit of measure for the statistic. For example, the units for the Amazon EC2 NetworkIn metric are Bytes because NetworkIn tracks the number of bytes that an instance receives on all network interfaces. You can also specify a unit when you create a custom metric. Units help provide conceptual meaning to your data. Metric data points that specify a unit of measure, such as Percent, are aggregated separately.

   

  If you specify a unit, you must use a unit that is appropriate for the metric. Otherwise, the CloudWatch alarm can get stuck in the ``INSUFFICIENT DATA`` state. 

  

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

  

  

``--evaluation-periods`` (integer)


  The number of periods over which data is compared to the specified threshold. An alarm's total current evaluation period can be no longer than one day, so this number multiplied by ``period`` must be 86,400 or less.

  

``--threshold`` (double)


  The value against which the specified statistic is compared.

  

``--comparison-operator`` (string)


  The arithmetic operation to use when comparing the specified statistic and threshold. The specified statistic value is used as the first operand.

  

  Possible values:

  
  *   ``GreaterThanOrEqualToThreshold``

  
  *   ``GreaterThanThreshold``

  
  *   ``LessThanThreshold``

  
  *   ``LessThanOrEqualToThreshold``

  

  

``--treat-missing-data`` (string)


  Sets how this alarm is to handle missing data points. If ``treat-missing-data`` is omitted, the default behavior of ``missing`` is used. For more information, see `Configuring How CloudWatch Alarms Treats Missing Data <http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html#alarms-and-missing-data>`_ .

   

  Valid Values: ``breaching | notBreaching | ignore | missing``  

  

``--evaluate-low-sample-count-percentile`` (string)


  Used only for alarms based on percentiles. If you specify ``ignore`` , the alarm state does not change during periods with too few data points to be statistically significant. If you specify ``evaluate`` or omit this parameter, the alarm is always evaluated and possibly changes state no matter how many data points are available. For more information, see `Percentile-Based CloudWatch Alarms and Low Data Samples <http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html#percentiles-with-low-samples>`_ .

   

  Valid Values: ``evaluate | ignore``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To send an Amazon Simple Notification Service email message when CPU utilization exceeds 70 percent**

The following example uses the ``put-metric-alarm`` command to send an Amazon Simple Notification Service email message when CPU utilization exceeds 70 percent::

  aws cloudwatch put-metric-alarm --alarm-name cpu-mon --alarm-description "Alarm when CPU exceeds 70 percent" --metric-name CPUUtilization --namespace AWS/EC2 --statistic Average --period 300 --threshold 70 --comparison-operator GreaterThanThreshold  --dimensions "Name=InstanceId,Value=i-12345678" --evaluation-periods 2 --alarm-actions arn:aws:sns:us-east-1:111122223333:MyTopic --unit Percent

This command returns to the prompt if successful. If an alarm with the same name already exists, it will be overwritten by the new alarm.

**To specify multiple dimensions**

The following example illustrates how to specify multiple dimensions. Each dimension is specified as a Name/Value pair, with a comma between the name and the value. Multiple dimensions are separated by a space::

  aws cloudwatch put-metric-alarm --alarm-name "Default_Test_Alarm3" --alarm-description "The default example alarm" --namespace "CW EXAMPLE METRICS" --metric-name Default_Test --statistic Average --period 60 --evaluation-periods 3 --threshold 50 --comparison-operator GreaterThanOrEqualToThreshold --dimensions Name=key1,Value=value1 Name=key2,Value=value2


======
Output
======

None