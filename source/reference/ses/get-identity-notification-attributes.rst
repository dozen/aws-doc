[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses get-identity-notification-attributes:


************************************
get-identity-notification-attributes
************************************



===========
Description
===========



Given a list of verified identities (email addresses and/or domains), returns a structure describing identity notification attributes.

 

This action is throttled at one request per second and can only get notification attributes for up to 100 identities at a time.

 

For more information about using notifications with Amazon SES, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/notifications.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/GetIdentityNotificationAttributes>`_


========
Synopsis
========

::

    get-identity-notification-attributes
  --identities <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identities`` (list)


  A list of one or more identities. You can specify an identity by using its name or by using its Amazon Resource Name (ARN). Examples: ``user@example.com`` , ``example.com`` , ``arn:aws:ses:us-east-1:123456789012:identity/example.com`` .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the Amazon SES notification attributes for a list of identities**

The following example uses the ``get-identity-notification-attributes`` command to retrieve the Amazon SES notification attributes for a list of identities::

    aws ses get-identity-notification-attributes --identities "user1@example.com" "user2@example.com"

Output::

 {
    "NotificationAttributes": {
        "user1@example.com": {
            "ForwardingEnabled": false,
            "ComplaintTopic": "arn:aws:sns:us-east-1:EXAMPLE65304:MyTopic",
            "BounceTopic": "arn:aws:sns:us-east-1:EXAMPLE65304:MyTopic",
            "DeliveryTopic": "arn:aws:sns:us-east-1:EXAMPLE65304:MyTopic"
        },
        "user2@example.com": {
            "ForwardingEnabled": true
        }
    }
 }

This command returns the status of email feedback forwarding and, if applicable, the Amazon Resource Names (ARNs) of the Amazon SNS topics that bounce, complaint, and delivery notifications are sent to.

If you call this command with an identity that you have never submitted for verification, that identity won't appear in the output.

For more information about notifications, see `Using Notifications With Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Using Notifications With Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/notifications.html


======
Output
======

NotificationAttributes -> (map)

  

  A map of Identity to IdentityNotificationAttributes.

  

  key -> (string)

    

    

  value -> (structure)

    

    Represents the notification attributes of an identity, including whether an identity has Amazon Simple Notification Service (Amazon SNS) topics set for bounce, complaint, and/or delivery notifications, and whether feedback forwarding is enabled for bounce and complaint notifications.

    

    BounceTopic -> (string)

      

      The Amazon Resource Name (ARN) of the Amazon SNS topic where Amazon SES will publish bounce notifications.

      

      

    ComplaintTopic -> (string)

      

      The Amazon Resource Name (ARN) of the Amazon SNS topic where Amazon SES will publish complaint notifications.

      

      

    DeliveryTopic -> (string)

      

      The Amazon Resource Name (ARN) of the Amazon SNS topic where Amazon SES will publish delivery notifications.

      

      

    ForwardingEnabled -> (boolean)

      

      Describes whether Amazon SES will forward bounce and complaint notifications as email. ``true`` indicates that Amazon SES will forward bounce and complaint notifications as email, while ``false`` indicates that bounce and complaint notifications will be published only to the specified bounce and complaint Amazon SNS topics.

      

      

    HeadersInBounceNotificationsEnabled -> (boolean)

      

      Describes whether Amazon SES includes the original email headers in Amazon SNS notifications of type ``Bounce`` . A value of ``true`` specifies that Amazon SES will include headers in bounce notifications, and a value of ``false`` specifies that Amazon SES will not include headers in bounce notifications.

      

      

    HeadersInComplaintNotificationsEnabled -> (boolean)

      

      Describes whether Amazon SES includes the original email headers in Amazon SNS notifications of type ``Complaint`` . A value of ``true`` specifies that Amazon SES will include headers in complaint notifications, and a value of ``false`` specifies that Amazon SES will not include headers in complaint notifications.

      

      

    HeadersInDeliveryNotificationsEnabled -> (boolean)

      

      Describes whether Amazon SES includes the original email headers in Amazon SNS notifications of type ``Delivery`` . A value of ``true`` specifies that Amazon SES will include headers in delivery notifications, and a value of ``false`` specifies that Amazon SES will not include headers in delivery notifications.

      

      

    

  

