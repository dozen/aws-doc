[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns get-subscription-attributes:


***************************
get-subscription-attributes
***************************



===========
Description
===========



Returns all of the properties of a subscription.



========
Synopsis
========

::

    get-subscription-attributes
  --subscription-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--subscription-arn`` (string)


  The ARN of the subscription whose properties you want to get.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command gets the attributes of a subscription to a topic named ``my-topic``::

  aws sns get-subscription-attributes --subscription-arn "arn:aws:sns:us-west-2:0123456789012:my-topic:8a21d249-4329-4871-acc6-7be709c6ea7f"

The ``subscription-arn`` is available in the output of ``aws sns list-subscriptions``.

Output::

  {
      "Attributes": {
          "Endpoint": "my-email@example.com",
          "Protocol": "email",
          "RawMessageDelivery": "false",
          "ConfirmationWasAuthenticated": "false",
          "Owner": "0123456789012",
          "SubscriptionArn": "arn:aws:sns:us-west-2:0123456789012:my-topic:8a21d249-4329-4871-acc6-7be709c6ea7f",
          "TopicArn": "arn:aws:sns:us-west-2:0123456789012:my-topic"
      }
  }

======
Output
======

Attributes -> (map)

  

  A map of the subscription's attributes. Attributes in this map include the following:

   

   
  * ``SubscriptionArn`` -- the subscription's ARN
   
  * ``TopicArn`` -- the topic ARN that the subscription is associated with
   
  * ``Owner`` -- the AWS account ID of the subscription's owner
   
  * ``ConfirmationWasAuthenticated`` -- true if the subscription confirmation request was authenticated
   
  * ``DeliveryPolicy`` -- the JSON serialization of the subscription's delivery policy
   
  * ``EffectiveDeliveryPolicy`` -- the JSON serialization of the effective delivery policy that takes into account the topic delivery policy and account system defaults
   

  

  key -> (string)

    

    

  value -> (string)

    

    

  

