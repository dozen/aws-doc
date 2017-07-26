[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-auto-scaling-notification-types:


****************************************
describe-auto-scaling-notification-types
****************************************



===========
Description
===========



Describes the notification types that are supported by Auto Scaling.



========
Synopsis
========

::

    describe-auto-scaling-notification-types
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe the Auto Scaling notification types**

This example describes the available notification types::

	aws autoscaling describe-auto-scaling-notification-types

The following is example output::

	{
		"AutoScalingNotificationTypes": [
			"autoscaling:EC2_INSTANCE_LAUNCH",
			"autoscaling:EC2_INSTANCE_LAUNCH_ERROR",
			"autoscaling:EC2_INSTANCE_TERMINATE",
			"autoscaling:EC2_INSTANCE_TERMINATE_ERROR",
			"autoscaling:TEST_NOTIFICATION"
		]
	}

For more information, see `Configure Your Auto Scaling Group to Send Notifications`_ in the *Auto Scaling Developer Guide*.

.. _`Configure Your Auto Scaling Group to Send Notifications`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ASGettingNotifications.html#as-configure-asg-for-sns


======
Output
======

AutoScalingNotificationTypes -> (list)

  

  One or more of the following notification types:

   

   
  * ``autoscaling:EC2_INSTANCE_LAUNCH`` 
   
  * ``autoscaling:EC2_INSTANCE_LAUNCH_ERROR`` 
   
  * ``autoscaling:EC2_INSTANCE_TERMINATE`` 
   
  * ``autoscaling:EC2_INSTANCE_TERMINATE_ERROR`` 
   
  * ``autoscaling:TEST_NOTIFICATION`` 
   

  

  (string)

    

    

  

