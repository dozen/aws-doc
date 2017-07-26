[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway update-gateway-software-now:


***************************
update-gateway-software-now
***************************



===========
Description
===========



This operation updates the gateway virtual machine (VM) software. The request immediately triggers the software update. 

 

.. note::

  When you make this request, you get a ``200 OK`` success response immediately. However, it might take some time for the update to complete. You can call  describe-gateway-information to verify the gateway is in the ``STATE_RUNNING`` state.

 

.. warning::

  A software update forces a system restart of your gateway. You can minimize the chance of any disruption to your applications by increasing your iSCSI Initiators' timeouts. For more information about increasing iSCSI Initiator timeouts for Windows and Linux, see `Customizing Your Windows iSCSI Settings`_ and `Customizing Your Linux iSCSI Settings`_ , respectively.



========
Synopsis
========

::

    update-gateway-software-now
  --gateway-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  



.. _Customizing Your Linux iSCSI Settings: http://docs.aws.amazon.com/storagegateway/latest/userguide/ConfiguringiSCSIClientInitiatorRedHatClient.html#CustomizeLinuxiSCSISettings
.. _Customizing Your Windows iSCSI Settings: http://docs.aws.amazon.com/storagegateway/latest/userguide/ConfiguringiSCSIClientInitiatorWindowsClient.html#CustomizeWindowsiSCSISettings
