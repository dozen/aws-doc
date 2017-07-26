[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway shutdown-gateway:


****************
shutdown-gateway
****************



===========
Description
===========



Shuts down a gateway. To specify which gateway to shut down, use the Amazon Resource Name (ARN) of the gateway in the body of your request.

 

The operation shuts down the gateway service component running in the gateway's virtual machine (VM) and not the host VM.

 

.. note::

   

  If you want to shut down the VM, it is recommended that you first shut down the gateway component in the VM to avoid unpredictable conditions.

   

 

After the gateway is shutdown, you cannot call any other API except  start-gateway ,  describe-gateway-information , and  list-gateways . For more information, see  activate-gateway . Your applications cannot read from or write to the gateway's storage volumes, and there are no snapshots taken.

 

.. note::

   

  When you make a shutdown request, you will get a ``200 OK`` success response immediately. However, it might take some time for the gateway to shut down. You can call the  describe-gateway-information API to check the status. For more information, see  activate-gateway .

   

 

If do not intend to use the gateway again, you must delete the gateway (using  delete-gateway ) to no longer pay software charges associated with the gateway.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/ShutdownGateway>`_


========
Synopsis
========

::

    shutdown-gateway
  --gateway-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

