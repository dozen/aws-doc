[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway update-gateway-information:


**************************
update-gateway-information
**************************



===========
Description
===========



This operation updates a gateway's metadata, which includes the gateway's name and time zone. To specify which gateway to update, use the Amazon Resource Name (ARN) of the gateway in your request.

 

.. note::

  For Gateways activated after September 02, 2015, the gateway's ARN contains the gateway id rather than the gateway name. However changing the name of the gateway has no effect on the gateway's ARN.



========
Synopsis
========

::

    update-gateway-information
  --gateway-arn <value>
  [--gateway-name <value>]
  [--gateway-timezone <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--gateway-name`` (string)


  The name you configured for your gateway.

  

``--gateway-timezone`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

GatewayName -> (string)

  

  

