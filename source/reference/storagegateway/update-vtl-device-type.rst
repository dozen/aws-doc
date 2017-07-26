[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway update-vtl-device-type:


**********************
update-vtl-device-type
**********************



===========
Description
===========



This operation updates the type of medium changer in a gateway-VTL. When you activate a gateway-VTL, you select a medium changer type for the gateway-VTL. This operation enables you to select a different type of medium changer after a gateway-VTL is activated.



========
Synopsis
========

::

    update-vtl-device-type
  --vtl-device-arn <value>
  --device-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--vtl-device-arn`` (string)


  The Amazon Resource Name (ARN) of the medium changer you want to select.

  

``--device-type`` (string)


  The type of medium changer you want to select.

   

  *Valid Values* : "STK-L700", "AWS-Gateway-VTL"

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

VTLDeviceARN -> (string)

  

  The Amazon Resource Name (ARN) of the medium changer you have selected.

  

  

