[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling delete-notification-configuration:


*********************************
delete-notification-configuration
*********************************



===========
Description
===========



Deletes the specified notification.



========
Synopsis
========

::

    delete-notification-configuration
  --auto-scaling-group-name <value>
  --topic-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--topic-arn`` (string)


  The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) topic.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete an Auto Scaling notification**

This example deletes the specified notification from the specified Auto Scaling group::

	aws autoscaling delete-notification-configuration --auto-scaling-group-name my-auto-scaling-group --topic-arn arn:aws:sns:us-west-2:123456789012:my-sns-topic

For more information, see `Delete the Notification Configuration`_ in the *Auto Scaling Developer Guide*.

.. _`Delete the Notification Configuration`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ASGettingNotifications.html#delete-settingupnotifications



======
Output
======

None