[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling put-notification-configuration:


******************************
put-notification-configuration
******************************



===========
Description
===========



Configures an Auto Scaling group to send notifications when specified events take place. Subscribers to the specified topic can have messages delivered to an endpoint such as a web server or an email address.

 

This configuration overwrites any existing configuration.

 

For more information see `Getting SNS Notifications When Your Auto Scaling Group Scales <http://docs.aws.amazon.com/autoscaling/latest/userguide/ASGettingNotifications.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/PutNotificationConfiguration>`_


========
Synopsis
========

::

    put-notification-configuration
  --auto-scaling-group-name <value>
  --topic-arn <value>
  --notification-types <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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