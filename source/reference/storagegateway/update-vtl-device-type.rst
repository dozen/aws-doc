[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway update-vtl-device-type:


**********************
update-vtl-device-type
**********************



===========
Description
===========



Updates the type of medium changer in a tape gateway. When you activate a tape gateway, you select a medium changer type for the tape gateway. This operation enables you to select a different type of medium changer after a tape gateway is activated. This operation is only supported in the tape gateway architecture.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/UpdateVTLDeviceType>`_


========
Synopsis
========

::

    update-vtl-device-type
  --vtl-device-arn <value>
  --device-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--vtl-device-arn`` (string)


  The Amazon Resource Name (ARN) of the medium changer you want to select.

  

``--device-type`` (string)


  The type of medium changer you want to select.

   

  Valid Values: "STK-L700", "AWS-Gateway-VTL"

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

VTLDeviceARN -> (string)

  

  The Amazon Resource Name (ARN) of the medium changer you have selected.

  

  

