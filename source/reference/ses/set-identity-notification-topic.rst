[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses set-identity-notification-topic:


*******************************
set-identity-notification-topic
*******************************



===========
Description
===========



Given an identity (email address or domain), sets the Amazon Simple Notification Service (Amazon SNS) topic to which Amazon SES will publish bounce, complaint, and/or delivery notifications for emails sent with that identity as the ``Source`` .

 

.. note::

  Unless feedback forwarding is enabled, you must specify Amazon SNS topics for bounce and complaint notifications. For more information, see ``set-identity-feedback-forwarding-enabled`` . 

 

This action is throttled at one request per second.

 

For more information about feedback notification, see the `Amazon SES Developer Guide`_ .



========
Synopsis
========

::

    set-identity-notification-topic
  --identity <value>
  --notification-type <value>
  [--sns-topic <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity`` (string)


  The identity for which the Amazon SNS topic will be set. You can specify an identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

  

``--notification-type`` (string)


  The type of notifications that will be published to the specified Amazon SNS topic.

  

  Possible values:

  
  *   ``Bounce``

  
  *   ``Complaint``

  
  *   ``Delivery``

  

  

``--sns-topic`` (string)


  The Amazon Resource Name (ARN) of the Amazon SNS topic. If the parameter is omitted from the request or a null value is passed, ``SnsTopic`` is cleared and publishing is disabled.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To set the Amazon SNS topic to which Amazon SES will publish bounce, complaint, and/or delivery notifications for a verified identity**

The following example uses the ``set-identity-notification-topic`` command to specify the Amazon SNS topic to which a verified email address will receive bounce notifications::

    aws ses set-identity-notification-topic --identity user@example.com --notification-type Bounce --sns-topic arn:aws:sns:us-east-1:EXAMPLE65304:MyTopic

For more information about notifications, see `Using Notifications With Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Using Notifications With Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/notifications.html



======
Output
======



.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/notifications.html
