[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch put-metric-alarm:


****************
put-metric-alarm
****************



===========
Description
===========



Creates or updates an alarm and associates it with the specified Amazon CloudWatch metric. Optionally, this operation can associate one or more Amazon Simple Notification Service resources with the alarm. 

 

When this operation creates an alarm, the alarm state is immediately set to ``INSUFFICIENT_DATA`` . The alarm is evaluated and its ``StateValue`` is set appropriately. Any actions associated with the ``StateValue`` is then executed. 

 

.. note::

  When updating an existing alarm, its ``StateValue`` is left unchanged. 

 

.. note::

  If you are using an AWS Identity and Access Management (IAM) account to create or modify an alarm, you must have the following Amazon EC2 permissions: 

   
  * ``ec2:DescribeInstanceStatus`` and ``ec2:DescribeInstances`` for all alarms on Amazon EC2 instance status metrics.
   
  * ``ec2:StopInstances`` for alarms with stop actions.
   
  * ``ec2:TerminateInstances`` for alarms with terminate actions.
   
  * ``ec2:DescribeInstanceRecoveryAttribute`` , and ``ec2:RecoverInstances`` for alarms with recover actions.
   

   

  If you have read/write permissions for Amazon CloudWatch but not for Amazon EC2, you can still create an alarm but the stop or terminate actions won't be performed on the Amazon EC2 instance. However, if you are later granted permission to use the associated Amazon EC2 APIs, the alarm actions you created earlier will be performed. For more information about IAM permissions, see `Permissions and Policies`_ in *Using IAM* .

   

  If you are using an IAM role (e.g., an Amazon EC2 instance profile), you cannot stop or terminate the instance using alarm actions. However, you can still see the alarm state and perform any other actions such as Amazon SNS notifications or Auto Scaling policies.

   

  If you are using temporary security credentials granted using the AWS Security Token Service (AWS STS), you cannot stop or terminate an Amazon EC2 instance using alarm actions.

   



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
  --statistic <value>
  [--dimensions <value>]
  --period <value>
  [--unit <value>]
  --evaluation-periods <value>
  --threshold <value>
  --comparison-operator <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--alarm-name`` (string)


  The descriptive name for the alarm. This name must be unique within the user's AWS account 

  

``--alarm-description`` (string)


  The description for the alarm. 

  

``--actions-enabled`` | ``--no-actions-enabled`` (boolean)


  Indicates whether or not actions should be executed during any changes to the alarm's state. 

  

``--ok-actions`` (list)


  The list of actions to execute when this alarm transitions into an ``OK`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

   

  Valid Values: arn:aws:automate:*region (e.g., us-east-1)* :ec2:stop | arn:aws:automate:*region (e.g., us-east-1)* :ec2:terminate | arn:aws:automate:*region (e.g., us-east-1)* :ec2:recover

   

  Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

   

  **Note:** You must create at least one stop, terminate, or reboot alarm using the Amazon EC2 or CloudWatch console to create the **EC2ActionsAccess** IAM role for the first time. After this IAM role is created, you can create stop, terminate, or reboot alarms using the CLI.

  



Syntax::

  "string" "string" ...



``--alarm-actions`` (list)


  The list of actions to execute when this alarm transitions into an ``ALARM`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

   

  Valid Values: arn:aws:automate:*region (e.g., us-east-1)* :ec2:stop | arn:aws:automate:*region (e.g., us-east-1)* :ec2:terminate | arn:aws:automate:*region (e.g., us-east-1)* :ec2:recover

   

  Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

   

  **Note:** You must create at least one stop, terminate, or reboot alarm using the Amazon EC2 or CloudWatch console to create the **EC2ActionsAccess** IAM role for the first time. After this IAM role is created, you can create stop, terminate, or reboot alarms using the CLI.

  



Syntax::

  "string" "string" ...



``--insufficient-data-actions`` (list)


  The list of actions to execute when this alarm transitions into an ``INSUFFICIENT_DATA`` state from any other state. Each action is specified as an Amazon Resource Name (ARN). 

   

  Valid Values: arn:aws:automate:*region (e.g., us-east-1)* :ec2:stop | arn:aws:automate:*region (e.g., us-east-1)* :ec2:terminate | arn:aws:automate:*region (e.g., us-east-1)* :ec2:recover

   

  Valid Values (for use with IAM roles): arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Stop/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Terminate/1.0 | arn:aws:swf:us-east-1:{*customer-account* }:action/actions/AWS_EC2.InstanceId.Reboot/1.0

   

  **Note:** You must create at least one stop, terminate, or reboot alarm using the Amazon EC2 or CloudWatch console to create the **EC2ActionsAccess** IAM role for the first time. After this IAM role is created, you can create stop, terminate, or reboot alarms using the CLI.

  



Syntax::

  "string" "string" ...



``--metric-name`` (string)


  The name for the alarm's associated metric. 

  

``--namespace`` (string)


  The namespace for the alarm's associated metric. 

  

``--statistic`` (string)


  The statistic to apply to the alarm's associated metric. 

  

  Possible values:

  
  *   ``SampleCount``

  
  *   ``Average``

  
  *   ``Sum``

  
  *   ``Minimum``

  
  *   ``Maximum``

  

  

``--dimensions`` (list)


  The dimensions for the alarm's associated metric. 

  



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


  The period in seconds over which the specified statistic is applied. 

  

``--unit`` (string)


  The statistic's unit of measure. For example, the units for the Amazon EC2 NetworkIn metric are Bytes because NetworkIn tracks the number of bytes that an instance receives on all network interfaces. You can also specify a unit when you create a custom metric. Units help provide conceptual meaning to your data. Metric data points that specify a unit of measure, such as Percent, are aggregated separately. 

   

   **Note:** If you specify a unit, you must use a unit that is appropriate for the metric. Otherwise, this can cause an Amazon CloudWatch alarm to get stuck in the INSUFFICIENT DATA state. 

  

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


  The number of periods over which data is compared to the specified threshold. 

  

``--threshold`` (double)


  The value against which the specified statistic is compared. 

  

``--comparison-operator`` (string)


  The arithmetic operation to use when comparing the specified ``statistic`` and ``threshold`` . The specified ``statistic`` value is used as the first operand. 

  

  Possible values:

  
  *   ``GreaterThanOrEqualToThreshold``

  
  *   ``GreaterThanThreshold``

  
  *   ``LessThanThreshold``

  
  *   ``LessThanOrEqualToThreshold``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To send an Amazon Simple Notification Service email message when CPU utilization exceeds 70 percent**

The following example uses the ``put-metric-alarm`` command to send an Amazon Simple Notification Service email message when CPU utilization exceeds 70 percent::

  aws cloudwatch put-metric-alarm --alarm-name cpu-mon --alarm-description "Alarm when CPU exceeds 70 percent" --metric-name CPUUtilization --namespace AWS/EC2 --statistic Average --period 300 --threshold 70 --comparison-operator GreaterThanThreshold  --dimensions  Name=InstanceId,Value=i-12345678 --evaluation-periods 2 --alarm-actions arn:aws:sns:us-east-1:111122223333:MyTopic --unit Percent

This command returns to the prompt if successful. If an alarm with the same name already exists, it will be overwritten by the new alarm.


======
Output
======

None

.. _Permissions and Policies: http://docs.aws.amazon.com//IAM/latest/UserGuide/PermissionsAndPolicies.html
