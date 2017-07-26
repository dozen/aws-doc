[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns confirm-subscription:


********************
confirm-subscription
********************



===========
Description
===========



Verifies an endpoint owner's intent to receive messages by validating the token sent to the endpoint by an earlier ``subscribe`` action. If the token is valid, the action creates a new subscription and returns its Amazon Resource Name (ARN). This call requires an AWS signature only when the ``AuthenticateOnUnsubscribe`` flag is set to "true".



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/ConfirmSubscription>`_


========
Synopsis
========

::

    confirm-subscription
  --topic-arn <value>
  --token <value>
  [--authenticate-on-unsubscribe <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--topic-arn`` (string)


  The ARN of the topic for which you wish to confirm a subscription.

  

``--token`` (string)


  Short-lived token sent to an endpoint during the ``subscribe`` action.

  

``--authenticate-on-unsubscribe`` (string)


  Disallows unauthenticated unsubscribes of the subscription. If the value of this parameter is ``true`` and the request has an AWS signature, then only the topic owner and the subscription owner can unsubscribe the endpoint. The unsubscribe action requires AWS authentication. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command confirms a subscription to an SNS topic named ``my-topic``::

  aws sns confirm-subscription --topic-arn arn:aws:sns:us-west-2:0123456789012:my-topic --token 2336412f37fb687f5d51e6e241d7700ae02f7124d8268910b858cb4db727ceeb2474bb937929d3bdd7ce5d0cce19325d036bc858d3c217426bcafa9c501a2cace93b83f1dd3797627467553dc438a8c974119496fc3eff026eaa5d14472ded6f9a5c43aec62d83ef5f49109da7176391

The token is included in the confirmation message sent to the notification endpoint specified in the subscribe call.

Output::

  {
      "SubscriptionArn": "arn:aws:sns:us-west-2:0123456789012:my-topic:8a21d249-4329-4871-acc6-7be709c6ea7f"
  }


======
Output
======

SubscriptionArn -> (string)

  

  The ARN of the created subscription.

  

  

