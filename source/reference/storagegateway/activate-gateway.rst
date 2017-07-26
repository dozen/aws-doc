[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway activate-gateway:


****************
activate-gateway
****************



===========
Description
===========



This operation activates the gateway you previously deployed on your host. For more information, see `Activate the AWS Storage Gateway`_ . In the activation process, you specify information such as the region you want to use for storing snapshots, the time zone for scheduled snapshots the gateway snapshot schedule window, an activation key, and a name for your gateway. The activation process also associates your gateway with your account; for more information, see  update-gateway-information .

 

.. note::

  You must turn on the gateway VM before you can activate your gateway.



========
Synopsis
========

::

    activate-gateway
  --activation-key <value>
  --gateway-name <value>
  --gateway-timezone <value>
  --gateway-region <value>
  [--gateway-type <value>]
  [--tape-drive-type <value>]
  [--medium-changer-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--activation-key`` (string)


  Your gateway activation key. You can obtain the activation key by sending an HTTP GET request with redirects enabled to the gateway IP address (port 80). The redirect URL returned in the response provides you the activation key for your gateway in the query string parameter ``activationKey`` . It may also include other activation-related parameters, however, these are merely defaults -- the arguments you pass to the ``activate-gateway`` API call determine the actual configuration of your gateway.

  

``--gateway-name`` (string)


  The name you configured for your gateway.

  

``--gateway-timezone`` (string)


  A value that indicates the time zone you want to set for the gateway. The time zone is used, for example, for scheduling snapshots and your gateway's maintenance schedule.

  

``--gateway-region`` (string)


  A value that indicates the region where you want to store the snapshot backups. The gateway region specified must be the same region as the region in your ``Host`` header in the request. For more information about available regions and endpoints for AWS Storage Gateway, see `Regions and Endpoints`_ in the *Amazon Web Services Glossary* .

   

  *Valid Values* : "us-east-1", "us-west-1", "us-west-2", "eu-west-1", "eu-central-1", "ap-northeast-1", "ap-southeast-1", "ap-southeast-2", "sa-east-1"

  

``--gateway-type`` (string)


  A value that defines the type of gateway to activate. The type specified is critical to all later functions of the gateway and cannot be changed after activation. The default value is ``STORED`` . 

  

``--tape-drive-type`` (string)


  The value that indicates the type of tape drive to use for gateway-VTL. This field is optional. 

   

  *Valid Values* : "IBM-ULT3580-TD5" 

  

``--medium-changer-type`` (string)


  The value that indicates the type of medium changer to use for gateway-VTL. This field is optional.

   

  *Valid Values* : "STK-L700", "AWS-Gateway-VTL"

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  



.. _Activate the AWS Storage Gateway: http://docs.aws.amazon.com/storagegateway/latest/userguide/GettingStartedActivateGateway-common.html
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html#sg_region
