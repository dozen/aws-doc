[ :ref:`aws <cli:aws>` . :ref:`iot-data <cli:aws iot-data>` ]

.. _cli:aws iot-data publish:


*******
publish
*******



===========
Description
===========



Publishes state information.

 

For more information, see `HTTP Protocol <http://docs.aws.amazon.com/iot/latest/developerguide/protocols.html#http>`_ in the *AWS IoT Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-data-2015-05-28/Publish>`_


.. note::

    The default endpoint data.iot.[region].amazonaws.com is intended for testing purposes only. For production code it is strongly recommended to use the custom endpoint for your account  (retrievable via the iot describe-endpoint command) to ensure best availability and reachability of the service.




========
Synopsis
========

::

    publish
  --topic <value>
  [--qos <value>]
  [--payload <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--topic`` (string)


  The name of the MQTT topic.

  

``--qos`` (integer)


  The Quality of Service (QoS) level.

  

``--payload`` (blob)


  The state information, in JSON format.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None