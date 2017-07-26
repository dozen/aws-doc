[ :ref:`aws <cli:aws>` . :ref:`iot-data <cli:aws iot-data>` ]

.. _cli:aws iot-data publish:


*******
publish
*******



===========
Description
===========



Publishes state information.

 

For more information, see `HTTP Protocol`_ in the *AWS IoT Developer Guide* .



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
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _HTTP Protocol: http://docs.aws.amazon.com/iot/latest/developerguide/protocols.html#http
