[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-vpn-connection:


*********************
create-vpn-connection
*********************



===========
Description
===========



Creates a VPN connection between an existing virtual private gateway and a VPN customer gateway. The only supported connection type is ``ipsec.1`` .

 

The response includes information that you need to give to your network administrator to configure your customer gateway.

 

.. warning::

   

  We strongly recommend that you use HTTPS when calling this operation because the response contains sensitive cryptographic information for configuring your customer gateway.

   

 

If you decide to shut down your VPN connection for any reason and later create a new VPN connection, you must reconfigure your customer gateway with the new information returned from this call.

 

For more information about VPN connections, see `Adding a Hardware Virtual Private Gateway to Your VPC`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    create-vpn-connection
  [--dry-run | --no-dry-run]
  --type <value>
  --customer-gateway-id <value>
  --vpn-gateway-id <value>
  [--options <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--type`` (string)


  The type of VPN connection (``ipsec.1`` ).

  

``--customer-gateway-id`` (string)


  The ID of the customer gateway.

  

``--vpn-gateway-id`` (string)


  The ID of the virtual private gateway.

  

``--options`` (structure)


  Indicates whether the VPN connection requires static routes. If you are creating a VPN connection for a device that does not support BGP, you must specify ``true`` .

   

  Default: ``false`` 

  



Shorthand Syntax::

    StaticRoutesOnly=boolean




JSON Syntax::

  {
    "StaticRoutesOnly": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a VPN connection with dynamic routing**

This example creates a VPN connection between the specified virtual private gateway and the specified customer gateway. The output includes the configuration information that your network administrator needs, in XML format.

Command::

  aws ec2 create-vpn-connection --type ipsec.1 --customer-gateway-id cgw-0e11f167 --vpn-gateway-id vgw-9a4cacf3

Output::

  {
      "VpnConnection": {
          "VpnConnectionId": "vpn-40f41529"
          "CustomerGatewayConfiguration": "...configuration information...",
          "State": "available",
          "VpnGatewayId": "vgw-f211f09b",
          "CustomerGatewayId": "cgw-b4de3fdd"
      }
  }
  
**To create a VPN connection with static routing**

This example creates a VPN connection between the specified virtual private gateway and the specified customer gateway. The options specify static routing. The output includes the configuration information that your network administrator needs, in XML format.

Command::

  aws ec2 create-vpn-connection --type ipsec.1 --customer-gateway-id cgw-0e11f167 --vpn-gateway-id vgw-9a4cacf3 --options "{\"StaticRoutesOnly\":true}"

Output::

  {
      "VpnConnection": {
          "VpnConnectionId": "vpn-40f41529"
          "CustomerGatewayConfiguration": "...configuration information...",
          "State": "pending",
          "VpnGatewayId": "vgw-f211f09b",
          "CustomerGatewayId": "cgw-b4de3fdd",
          "Options": {
              "StaticRoutesOnly": true
          }          
      }
  }

======
Output
======

VpnConnection -> (structure)

  

  Information about the VPN connection.

  

  VpnConnectionId -> (string)

    

    The ID of the VPN connection.

    

    

  State -> (string)

    

    The current state of the VPN connection.

    

    

  CustomerGatewayConfiguration -> (string)

    

    The configuration information for the VPN connection's customer gateway (in the native XML format). This element is always present in the  create-vpn-connection response; however, it's present in the  describe-vpn-connections response only if the VPN connection is in the ``pending`` or ``available`` state.

    

    

  Type -> (string)

    

    The type of VPN connection.

    

    

  CustomerGatewayId -> (string)

    

    The ID of the customer gateway at your end of the VPN connection.

    

    

  VpnGatewayId -> (string)

    

    The ID of the virtual private gateway at the AWS side of the VPN connection.

    

    

  Tags -> (list)

    

    Any tags assigned to the VPN connection.

    

    (structure)

      

      Describes a tag.

      

      Key -> (string)

        

        The key of the tag. 

         

        Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

        

        

      Value -> (string)

        

        The value of the tag.

         

        Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

        

        

      

    

  VgwTelemetry -> (list)

    

    Information about the VPN tunnel.

    

    (structure)

      

      Describes telemetry for a VPN tunnel.

      

      OutsideIpAddress -> (string)

        

        The Internet-routable IP address of the virtual private gateway's outside interface.

        

        

      Status -> (string)

        

        The status of the VPN tunnel.

        

        

      LastStatusChange -> (timestamp)

        

        The date and time of the last change in status.

        

        

      StatusMessage -> (string)

        

        If an error occurs, a description of the error.

        

        

      AcceptedRouteCount -> (integer)

        

        The number of accepted routes.

        

        

      

    

  Options -> (structure)

    

    The VPN connection options.

    

    StaticRoutesOnly -> (boolean)

      

      Indicates whether the VPN connection uses static routes only. Static routes must be used for devices that don't support BGP.

      

      

    

  Routes -> (list)

    

    The static routes associated with the VPN connection.

    

    (structure)

      

      Describes a static route for a VPN connection.

      

      DestinationCidrBlock -> (string)

        

        The CIDR block associated with the local subnet of the customer data center.

        

        

      Source -> (string)

        

        Indicates how the routes were provided.

        

        

      State -> (string)

        

        The current state of the static route.

        

        

      

    

  



.. _Adding a Hardware Virtual Private Gateway to Your VPC: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_VPN.html
