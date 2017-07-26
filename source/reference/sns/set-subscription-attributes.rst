[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns set-subscription-attributes:


***************************
set-subscription-attributes
***************************



===========
Description
===========



Allows a subscription owner to set an attribute of the topic to a new value.



========
Synopsis
========

::

    set-subscription-attributes
  --subscription-arn <value>
  --attribute-name <value>
  [--attribute-value <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None