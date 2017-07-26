[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses set-identity-headers-in-notifications-enabled:


*********************************************
set-identity-headers-in-notifications-enabled
*********************************************



===========
Description
===========



Given an identity (an email address or a domain), sets whether Amazon SES includes the original email headers in the Amazon Simple Notification Service (Amazon SNS) notifications of a specified type.

 

This action is throttled at one request per second.

 

For more information about using notifications with Amazon SES, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/notifications.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/SetIdentityHeadersInNotificationsEnabled>`_


========
Synopsis
========

::

    set-identity-headers-in-notifications-enabled
  --identity <value>
  --notification-type <value>
  --enabled | --no-enabled
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity`` (string)


  The identity for which to enable or disable headers in notifications. Examples: ``user@example.com`` , ``example.com`` .

  

``--notification-type`` (string)


  The notification type for which to enable or disable headers in notifications. 

  

  Possible values:

  
  *   ``Bounce``

  
  *   ``Complaint``

  
  *   ``Delivery``

  

  

``--enabled`` | ``--no-enabled`` (boolean)


  Sets whether Amazon SES includes the original email headers in Amazon SNS notifications of the specified notification type. A value of ``true`` specifies that Amazon SES will include headers in notifications, and a value of ``false`` specifies that Amazon SES will not include headers in notifications.

   

  This value can only be set when ``notification-type`` is already set to use a particular Amazon SNS topic.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

