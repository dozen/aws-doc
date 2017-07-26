[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns set-subscription-attributes:


***************************
set-subscription-attributes
***************************



===========
Description
===========



Allows a subscription owner to set an attribute of the topic to a new value.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/SetSubscriptionAttributes>`_


========
Synopsis
========

::

    set-subscription-attributes
  --subscription-arn <value>
  --attribute-name <value>
  [--attribute-value <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subscription-arn`` (string)


  The ARN of the subscription to modify.

  

``--attribute-name`` (string)


  The name of the attribute you want to set. Only a subset of the subscriptions attributes are mutable.

   

  Valid values: ``DeliveryPolicy`` | ``RawMessageDelivery``  

  

``--attribute-value`` (string)


  The new value for the attribute in JSON format.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None