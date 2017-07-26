[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-lifecycle-hooks:


************************
describe-lifecycle-hooks
************************



===========
Description
===========



Describes the lifecycle hooks for the specified Auto Scaling group.



========
Synopsis
========

::

    describe-lifecycle-hooks
  --auto-scaling-group-name <value>
  [--lifecycle-hook-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the group.

  

``--lifecycle-hook-names`` (list)


  The names of one or more lifecycle hooks.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your lifecycle hooks**

This example describes the lifecycle hooks for the specified Auto Scaling group::

   aws autoscaling describe-lifecycle-hooks --auto-scaling-group-name my-auto-scaling-group
   
The following is example output::

  {
    "LifecycleHooks": [
        {
            "GlobalTimeout": 172800,
            "HeartbeatTimeout": 3600,
            "RoleARN": "arn:aws:iam::123456789012:role/my-auto-scaling-role",
            "AutoScalingGroupName": "my-auto-scaling-group",
            "LifecycleHookName": "my-lifecycle-hook",
            "DefaultResult": "ABANDON",
            "NotificationTargetARN": "arn:aws:sns:us-west-2:123456789012:my-sns-topic",
            "LifecycleTransition": "autoscaling:EC2_INSTANCE_LAUNCHING"
        }
    ]
  }


======
Output
======

LifecycleHooks -> (list)

  

  The lifecycle hooks for the specified group.

  

  (structure)

    

    Describes a lifecycle hook, which tells Auto Scaling that you want to perform an action when an instance launches or terminates. When you have a lifecycle hook in place, the Auto Scaling group will either:

     

     
    * Pause the instance after it launches, but before it is put into service
     
    * Pause the instance as it terminates, but before it is fully terminated
     

     

    For more information, see `Auto Scaling Lifecycle`_ in the *Auto Scaling Developer Guide* .

    

    LifecycleHookName -> (string)

      

      The name of the lifecycle hook.

      

      

    AutoScalingGroupName -> (string)

      

      The name of the Auto Scaling group for the lifecycle hook.

      

      

    LifecycleTransition -> (string)

      

      The state of the EC2 instance to which you want to attach the lifecycle hook. For a list of lifecycle hook types, see  describe-lifecycle-hook-types .

      

      

    NotificationTargetARN -> (string)

      

      The ARN of the notification target that Auto Scaling uses to notify you when an instance is in the transition state for the lifecycle hook. This ARN target can be either an SQS queue or an SNS topic. The notification message sent to the target includes the following:

       

       
      * Lifecycle action token
       
      * User account ID
       
      * Name of the Auto Scaling group
       
      * Lifecycle hook name
       
      * EC2 instance ID
       
      * Lifecycle transition
       
      * Notification metadata
       

      

      

    RoleARN -> (string)

      

      The ARN of the IAM role that allows the Auto Scaling group to publish to the specified notification target.

      

      

    NotificationMetadata -> (string)

      

      Additional information that you want to include any time Auto Scaling sends a message to the notification target.

      

      

    HeartbeatTimeout -> (integer)

      

      The maximum time, in seconds, that can elapse before the lifecycle hook times out. The default is 3600 seconds (1 hour). When the lifecycle hook times out, Auto Scaling performs the default action. You can prevent the lifecycle hook from timing out by calling  record-lifecycle-action-heartbeat .

      

      

    GlobalTimeout -> (integer)

      

      The maximum time, in seconds, that an instance can remain in a ``Pending:Wait`` or ``Terminating:Wait`` state. The default is 172800 seconds (48 hours).

      

      

    DefaultResult -> (string)

      

      Defines the action the Auto Scaling group should take when the lifecycle hook timeout elapses or if an unexpected failure occurs. The valid values are ``CONTINUE`` and ``ABANDON`` . The default value is ``CONTINUE`` .

      

      

    

  



.. _Auto Scaling Lifecycle: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AutoScalingGroupLifecycle.html
