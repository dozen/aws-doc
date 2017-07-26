[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs create-notification-subscription:


********************************
create-notification-subscription
********************************



===========
Description
===========



Configure WorkDocs to use Amazon SNS notifications.

 

The endpoint receives a confirmation message, and must confirm the subscription. For more information, see `Confirm the Subscription <http://docs.aws.amazon.com/sns/latest/dg/SendMessageToHttp.html#SendMessageToHttp.confirm>`_ in the *Amazon Simple Notification Service Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/CreateNotificationSubscription>`_


========
Synopsis
========

::

    create-notification-subscription
  --organization-id <value>
  --protocol <value>
  --subscription-type <value>
  --notification-endpoint <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--organization-id`` (string)


  The ID of the organization.

  

``--protocol`` (string)


  The protocol to use. The supported value is https, which delivers JSON-encoded messasges using HTTPS POST.

  

  Possible values:

  
  *   ``HTTPS``

  

  

``--subscription-type`` (string)


  The notification type.

  

  Possible values:

  
  *   ``ALL``

  

  

``--notification-endpoint`` (string)


  The endpoint to receive the notifications. If the protocol is HTTPS, the endpoint is a URL that begins with "https://".

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Subscription -> (structure)

  

  The subscription.

  

  SubscriptionId -> (string)

    

    The ID of the subscription.

    

    

  EndPoint -> (string)

    

    The endpoint of the subscription.

    

    

  Protocol -> (string)

    

    The protocol of the subscription.

    

    

  

