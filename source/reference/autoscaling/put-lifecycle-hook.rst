[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling put-lifecycle-hook:


******************
put-lifecycle-hook
******************



===========
Description
===========



Creates or updates a lifecycle hook for the specified Auto Scaling Group.

 

A lifecycle hook tells Auto Scaling that you want to perform an action on an instance that is not actively in service; for example, either when the instance launches or before the instance terminates.

 

This step is a part of the procedure for adding a lifecycle hook to an Auto Scaling group:

 

 
* (Optional) Create a Lambda function and a rule that allows CloudWatch Events to invoke your Lambda function when Auto Scaling launches or terminates instances. 
 
* (Optional) Create a notification target and an IAM role. The target can be either an Amazon SQS queue or an Amazon SNS topic. The role allows Auto Scaling to publish lifecycle notifications to the target. 
 
* **Create the lifecycle hook. Specify whether the hook is used when the instances launch or terminate.**   
 
* If you need more time, record the lifecycle action heartbeat to keep the instance in a pending state. 
 
* If you finish before the timeout period ends, complete the lifecycle action. 
 

 

For more information, see `Auto Scaling Lifecycle Hooks <http://docs.aws.amazon.com/autoscaling/latest/userguide/lifecycle-hooks.html>`_ in the *Auto Scaling User Guide* .

 

If you exceed your maximum limit of lifecycle hooks, which by default is 50 per Auto Scaling group, the call fails. For information about updating this limit, see `AWS Service Limits <http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html>`_ in the *Amazon Web Services General Reference* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/PutLifecycleHook>`_


========
Synopsis
========

::

    put-lifecycle-hook
  --lifecycle-hook-name <value>
  --auto-scaling-group-name <value>
  [--lifecycle-transition <value>]
  [--role-arn <value>]
  [--notification-target-arn <value>]
  [--notification-metadata <value>]
  [--heartbeat-timeout <value>]
  [--default-result <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--lifecycle-hook-name`` (string)


  The name of the lifecycle hook.

  

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group to which you want to assign the lifecycle hook.

  

``--lifecycle-transition`` (string)


  The instance state to which you want to attach the lifecycle hook. For a list of lifecycle hook types, see  describe-lifecycle-hook-types .

   

  This parameter is required for new lifecycle hooks, but optional when updating existing hooks.

  

``--role-arn`` (string)


  The ARN of the IAM role that allows the Auto Scaling group to publish to the specified notification target.

   

  This parameter is required for new lifecycle hooks, but optional when updating existing hooks.

  

``--notification-target-arn`` (string)


  The ARN of the notification target that Auto Scaling will use to notify you when an instance is in the transition state for the lifecycle hook. This target can be either an SQS queue or an SNS topic. If you specify an empty string, this overrides the current ARN.

   

  This operation uses the JSON format when sending notifications to an Amazon SQS queue, and an email key/value pair format when sending notifications to an Amazon SNS topic.

   

  When you specify a notification target, Auto Scaling sends it a test message. Test messages contains the following additional key/value pair: ``"Event": "autoscaling:TEST_NOTIFICATION"`` .

  

``--notification-metadata`` (string)


  Contains additional information that you want to include any time Auto Scaling sends a message to the notification target.

  

``--heartbeat-timeout`` (integer)


  The amount of time, in seconds, that can elapse before the lifecycle hook times out. When the lifecycle hook times out, Auto Scaling performs the default action. You can prevent the lifecycle hook from timing out by calling  record-lifecycle-action-heartbeat . The default is 3600 seconds (1 hour).

  

``--default-result`` (string)


  Defines the action the Auto Scaling group should take when the lifecycle hook timeout elapses or if an unexpected failure occurs. This parameter can be either ``CONTINUE`` or ``ABANDON`` . The default value is ``ABANDON`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a lifecycle hook**

This example creates a lifecycle hook::

    aws autoscaling put-lifecycle-hook --lifecycle-hook-name my-lifecycle-hook --auto-scaling-group-name my-auto-scaling-group --lifecycle-transition autoscaling:EC2_INSTANCE_LAUNCHING --notification-target-arn arn:aws:sns:us-west-2:123456789012:my-sns-topic --role-arn arn:aws:iam::123456789012:role/my-auto-scaling-role

For more information, see `Adding Lifecycle Hooks`_ in the *Auto Scaling Developer Guide*.

.. _`Adding Lifecycle Hooks`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/adding-lifecycle-hooks.html


======
Output
======

