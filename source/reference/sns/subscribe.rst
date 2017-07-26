[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns subscribe:


*********
subscribe
*********



===========
Description
===========



Prepares to subscribe an notification-endpoint by sending the notification-endpoint a confirmation message. To actually create a subscription, the notification-endpoint owner must call the ``confirm-subscription`` action with the token from the confirmation message. Confirmation tokens are valid for three days.



========
Synopsis
========

::

    subscribe
  --topic-arn <value>
  --protocol <value>
  [--notification-endpoint <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--topic-arn`` (string)


  The ARN of the topic you want to subscribe to.

  

``--protocol`` (string)


  The protocol you want to use. Supported protocols include:

   

   
  * ``http`` -- delivery of JSON-encoded message via HTTP POST
   
  * ``https`` -- delivery of JSON-encoded message via HTTPS POST
   
  * ``email`` -- delivery of message via SMTP
   
  * ``email-json`` -- delivery of JSON-encoded message via SMTP
   
  * ``sms`` -- delivery of message via SMS
   
  * ``sqs`` -- delivery of JSON-encoded message to an Amazon SQS queue
   
  * ``application`` -- delivery of JSON-encoded message to an EndpointArn for a mobile app and device.
   

  

``--notification-endpoint`` (string)


  The notification-endpoint that you want to receive notifications. Endpoints vary by protocol:

   

   
  * For the ``http`` protocol, the notification-endpoint is an URL beginning with "http://"
   
  * For the ``https`` protocol, the notification-endpoint is a URL beginning with "https://"
   
  * For the ``email`` protocol, the notification-endpoint is an email address
   
  * For the ``email-json`` protocol, the notification-endpoint is an email address
   
  * For the ``sms`` protocol, the notification-endpoint is a phone number of an SMS-enabled device
   
  * For the ``sqs`` protocol, the notification-endpoint is the ARN of an Amazon SQS queue
   
  * For the ``application`` protocol, the notification-endpoint is the EndpointArn of a mobile app and device.
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command subscribes an email address to a topic::

  aws sns subscribe --topic-arn arn:aws:sns:us-west-2:0123456789012:my-topic --protocol email --notification-endpoint my-email@example.com

Output::

  {
      "SubscriptionArn": "pending confirmation"
  }


======
Output
======

SubscriptionArn -> (string)

  

  The ARN of the subscription, if the service was able to create a subscription immediately (without requiring notification-endpoint owner confirmation).

  

  

