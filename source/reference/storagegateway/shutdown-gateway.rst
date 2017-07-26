[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway shutdown-gateway:


****************
shutdown-gateway
****************



===========
Description
===========



This operation shuts down a gateway. To specify which gateway to shut down, use the Amazon Resource Name (ARN) of the gateway in the body of your request.

 

The operation shuts down the gateway service component running in the storage gateway's virtual machine (VM) and not the VM.

 

.. note::

  If you want to shut down the VM, it is recommended that you first shut down the gateway component in the VM to avoid unpredictable conditions.

 

After the gateway is shutdown, you cannot call any other API except  start-gateway ,  describe-gateway-information , and  list-gateways . For more information, see  activate-gateway . Your applications cannot read from or write to the gateway's storage volumes, and there are no snapshots taken.

 

.. note::

  When you make a shutdown request, you will get a ``200 OK`` success response immediately. However, it might take some time for the gateway to shut down. You can call the  describe-gateway-information API to check the status. For more information, see  activate-gateway .

 

If do not intend to use the gateway again, you must delete the gateway (using  delete-gateway ) to no longer pay software charges associated with the gateway.



========
Synopsis
========

::

    shutdown-gateway
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

  

  

