[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling record-lifecycle-action-heartbeat:


*********************************
record-lifecycle-action-heartbeat
*********************************



===========
Description
===========



Records a heartbeat for the lifecycle action associated with the specified token or instance. This extends the timeout by the length of time defined using  put-lifecycle-hook .

 

This step is a part of the procedure for adding a lifecycle hook to an Auto Scaling group:

 

 
* (Optional) Create a Lambda function and a rule that allows CloudWatch Events to invoke your Lambda function when Auto Scaling launches or terminates instances.
 
* (Optional) Create a notification target and an IAM role. The target can be either an Amazon SQS queue or an Amazon SNS topic. The role allows Auto Scaling to publish lifecycle notifications to the target.
 
* Create the lifecycle hook. Specify whether the hook is used when the instances launch or terminate.
 
* **If you need more time, record the lifecycle action heartbeat to keep the instance in a pending state.** 
 
* If you finish before the timeout period ends, complete the lifecycle action.
 

 

For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling Developer Guide* .



========
Synopsis
========

::

    record-lifecycle-action-heartbeat
  --lifecycle-hook-name <value>
  --auto-scaling-group-name <value>
  [--lifecycle-action-token <value>]
  [--instance-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--lifecycle-hook-name`` (string)


  The name of the lifecycle hook.

  

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group for the hook.

  

``--lifecycle-action-token`` (string)


  A token that uniquely identifies a specific lifecycle action associated with an instance. Auto Scaling sends this token to the notification target you specified when you created the lifecycle hook.

  

``--instance-id`` (string)


  The ID of the instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To record a lifecycle action heartbeat**

This example records a lifecycle action heartbeat to keep the instance in a pending state::

   aws autoscaling record-lifecycle-action-heartbeat --lifecycle-hook-name my-lifecycle-hook --auto-scaling-group-name my-auto-scaling-group --lifecycle-action-token bcd2f1b8-9a78-44d3-8a7a-4dd07d7cf635


======
Output
======



.. _Auto Scaling Lifecycle: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AutoScalingGroupLifecycle.html
