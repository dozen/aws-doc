[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses set-identity-feedback-forwarding-enabled:


****************************************
set-identity-feedback-forwarding-enabled
****************************************



===========
Description
===========



Given an identity (an email address or a domain), enables or disables whether Amazon SES forwards bounce and complaint notifications as email. Feedback forwarding can only be disabled when Amazon Simple Notification Service (Amazon SNS) topics are specified for both bounces and complaints.

 

.. note::

   

  Feedback forwarding does not apply to delivery notifications. Delivery notifications are only available through Amazon SNS.

   

 

This action is throttled at one request per second.

 

For more information about using notifications with Amazon SES, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/notifications.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/SetIdentityFeedbackForwardingEnabled>`_


========
Synopsis
========

::

    set-identity-feedback-forwarding-enabled
  --identity <value>
  --forwarding-enabled | --no-forwarding-enabled
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity`` (string)


  The identity for which to set bounce and complaint notification forwarding. Examples: ``user@example.com`` , ``example.com`` .

  

``--forwarding-enabled`` | ``--no-forwarding-enabled`` (boolean)


  Sets whether Amazon SES will forward bounce and complaint notifications as email. ``true`` specifies that Amazon SES will forward bounce and complaint notifications as email, in addition to any Amazon SNS topic publishing otherwise specified. ``false`` specifies that Amazon SES will publish bounce and complaint notifications only through Amazon SNS. This value can only be set to ``false`` when Amazon SNS topics are set for both ``Bounce`` and ``Complaint`` notification types.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

