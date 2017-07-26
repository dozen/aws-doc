[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-gateway-information:


****************************
describe-gateway-information
****************************



===========
Description
===========



Returns metadata about a gateway such as its name, network interfaces, configured time zone, and the state (whether the gateway is running or not). To specify which gateway to describe, use the Amazon Resource Name (ARN) of the gateway in your request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DescribeGatewayInformation>`_


========
Synopsis
========

::

    describe-gateway-information
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



========
Examples
========

**To describe a gateway**

The following ``describe-gateway-information`` command returns metadata about the specified gateway.
To specify which gateway to describe, use the Amazon Resource Name (ARN) of the gateway in the command.

This examples specifies a gateway with the id ``sgw-12A3456B`` in account ``123456789012``::

  aws storagegateway describe-gateway-information --gateway-arn "arn:aws:storagegateway:us-west-2:123456789012:gateway/sgw-12A3456B"

This command outputs a JSON block that contains metadata about about the gateway such as its name,
network interfaces, configured time zone, and the state (whether the gateway is running or not).


======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

GatewayId -> (string)

  

  The unique identifier assigned to your gateway during activation. This ID becomes part of the gateway Amazon Resource Name (ARN), which you use as input for other operations.

  

  

GatewayName -> (string)

  

  The name you configured for your gateway.

  

  

GatewayTimezone -> (string)

  

  A value that indicates the time zone configured for the gateway.

  

  

GatewayState -> (string)

  

  A value that indicates the operating state of the gateway.

  

  

GatewayNetworkInterfaces -> (list)

  

  A  NetworkInterface array that contains descriptions of the gateway network interfaces.

  

  (structure)

    

    Describes a gateway's network interface.

    

    Ipv4Address -> (string)

      

      The Internet Protocol version 4 (IPv4) address of the interface.

      

      

    MacAddress -> (string)

      

      The Media Access Control (MAC) address of the interface.

       

      .. note::

         

        This is currently unsupported and will not be returned in output.

         

      

      

    Ipv6Address -> (string)

      

      The Internet Protocol version 6 (IPv6) address of the interface. *Currently not supported* .

      

      

    

  

GatewayType -> (string)

  

  The type of the gateway.

  

  

NextUpdateAvailabilityDate -> (string)

  

  The date on which an update to the gateway is available. This date is in the time zone of the gateway. If the gateway is not available for an update this field is not returned in the response.

  

  

LastSoftwareUpdate -> (string)

  

  The date on which the last software update was applied to the gateway. If the gateway has never been updated, this field does not return a value in the response.

  

  

