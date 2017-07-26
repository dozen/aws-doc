[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling put-notification-configuration:


******************************
put-notification-configuration
******************************



===========
Description
===========



Configures an Auto Scaling group to send notifications when specified events take place. Subscribers to this topic can have messages for events delivered to an endpoint such as a web server or email address. 

 

For more information see `Getting Notifications When Your Auto Scaling Group Changes`_ in the *Auto Scaling Developer Guide* .

 

This configuration overwrites an existing configuration.



========
Synopsis
========

::

    put-notification-configuration
  --auto-scaling-group-name <value>
  --topic-arn <value>
  --notification-types <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--topic-arn`` (string)


  The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) topic. 

  

``--notification-types`` (list)


  The type of event that will cause the notification to be sent. For details about notification types supported by Auto Scaling, see  describe-auto-scaling-notification-types .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To add an Auto Scaling notification**

This example adds the specified notification to the specified Auto Scaling group::

	aws autoscaling put-notification-configuration --auto-scaling-group-name my-auto-scaling-group --topic-arn arn:aws:sns:us-west-2:123456789012:my-sns-topic --notification-type autoscaling:TEST_NOTIFICATION

For more information, see `Configure Your Auto Scaling Group to Send Notifications`_ in the *Auto Scaling Developer Guide*.

.. _`Configure Your Auto Scaling Group to Send Notifications`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ASGettingNotifications.html#as-configure-asg-for-sns


======
Output
======

None

.. _Getting Notifications When Your Auto Scaling Group Changes: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ASGettingNotifications.html
