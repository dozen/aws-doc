[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses set-identity-notification-topic:


*******************************
set-identity-notification-topic
*******************************



===========
Description
===========



Given an identity (an email address or a domain), sets the Amazon Simple Notification Service (Amazon SNS) topic to which Amazon SES will publish bounce, complaint, and/or delivery notifications for emails sent with that identity as the ``Source`` .

 

.. note::

   

  Unless feedback forwarding is enabled, you must specify Amazon SNS topics for bounce and complaint notifications. For more information, see ``set-identity-feedback-forwarding-enabled`` .

   

 

This action is throttled at one request per second.

 

For more information about feedback notification, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/notifications.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/SetIdentityNotificationTopic>`_


========
Synopsis
========

::

    set-identity-notification-topic
  --identity <value>
  --notification-type <value>
  [--sns-topic <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

