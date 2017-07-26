[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses set-identity-feedback-forwarding-enabled:


****************************************
set-identity-feedback-forwarding-enabled
****************************************



===========
Description
===========



Given an identity (email address or domain), enables or disables whether Amazon SES forwards bounce and complaint notifications as email. Feedback forwarding can only be disabled when Amazon Simple Notification Service (Amazon SNS) topics are specified for both bounces and complaints.

 

.. note::

  Feedback forwarding does not apply to delivery notifications. Delivery notifications are only available through Amazon SNS.

 

This action is throttled at one request per second.

 

For more information about using notifications with Amazon SES, see the `Amazon SES Developer Guide`_ .



========
Synopsis
========

::

    set-identity-feedback-forwarding-enabled
  --identity <value>
  --forwarding-enabled | --no-forwarding-enabled
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity`` (string)


  The identity for which to set bounce and complaint notification forwarding. Examples: ``user@example.com`` , ``example.com`` .

  

``--forwarding-enabled`` | ``--no-forwarding-enabled`` (boolean)


  Sets whether Amazon SES will forward bounce and complaint notifications as email. ``true`` specifies that Amazon SES will forward bounce and complaint notifications as email, in addition to any Amazon SNS topic publishing otherwise specified. ``false`` specifies that Amazon SES will publish bounce and complaint notifications only through Amazon SNS. This value can only be set to ``false`` when Amazon SNS topics are set for both ``Bounce`` and ``Complaint`` notification types.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To enable or disable bounce and complaint email feedback forwarding for an Amazon SES verified identity**

The following example uses the ``set-identity-feedback-forwarding-enabled`` command to enable a verified email address to receive bounce and complaint notifications by email::

    aws ses set-identity-feedback-forwarding-enabled --identity user@example.com --forwarding-enabled

You are required to receive bounce and complaint notifications via either Amazon SNS or email feedback forwarding, so you can only disable email feedback forwarding if you select an Amazon SNS topic for both bounce and complaint notifications.

For more information about notifications, see `Using Notifications With Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Using Notifications With Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/notifications.html



======
Output
======



.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/notifications.html
