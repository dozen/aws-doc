[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice delete-delivery-channel:


***********************
delete-delivery-channel
***********************



===========
Description
===========



Deletes the delivery channel.

 

Before you can delete the delivery channel, you must stop the configuration recorder by using the  stop-configuration-recorder action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/DeleteDeliveryChannel>`_


========
Synopsis
========

::

    delete-delivery-channel
  --delivery-channel-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--delivery-channel-name`` (string)


  The name of the delivery channel to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a delivery channel**

The following command deletes the default delivery channel::

    aws configservice delete-delivery-channel --delivery-channel-name default

======
Output
======

None