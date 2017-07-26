[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpn-connections:


************************
describe-vpn-connections
************************



===========
Description
===========



Describes one or more of your VPN connections.

 

For more information about VPN connections, see `Adding a Hardware Virtual Private Gateway to Your VPC`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    describe-vpn-connections
  [--dry-run | --no-dry-run]
  [--vpn-connection-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpn-connection-ids`` (list)


  One or more VPN connection IDs.

   

  Default: Describes your VPN connections.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``customer-gateway-configuration`` - The configuration information for the customer gateway. 
   
  * ``customer-gateway-id`` - The ID of a customer gateway associated with the VPN connection. 
   
  * ``state`` - The state of the VPN connection (``pending`` | ``available`` | ``deleting`` | ``deleted`` ). 
   
  * ``option.static-routes-only`` - Indicates whether the connection has static routes only. Used for devices that do not support Border Gateway Protocol (BGP). 
   
  * ``route.destination-cidr-block`` - The destination CIDR block. This corresponds to the subnet used in a customer data center. 
   
  * ``bgp-asn`` - The BGP Autonomous System Number (ASN) associated with a BGP device. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``type`` - The type of VPN connection. Currently the only supported type is ``ipsec.1`` . 
   
  * ``vpn-connection-id`` - The ID of the VPN connection. 
   
  * ``vpn-gateway-id`` - The ID of a virtual private gateway associated with the VPN connection. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your VPN connections**

This example describes your VPN connections.

Command::

  aws ec2 describe-vpn-connections

Output::

  {
      "VpnConnections": {
          "VpnConnectionId": "vpn-40f41529"
          "CustomerGatewayConfiguration": "...configuration information...",
          "VgwTelemetry": [
              {
                  "Status": "DOWN",
                  "AcceptedRouteCount": 0,
                  "OutsideIpAddress": "72.21.209.192",
                  "LastStatusChange": "2013-02-04T20:19:34.000Z",
                  "StatusMessage": "IPSEC IS DOWN"
              },
              {
                  "Status": "DOWN",
                  "AcceptedRouteCount": 0,
                  "OutsideIpAddress": "72.21.209.224",
                  "LastStatusChange": "2013-02-04T20:19:34.000Z",
                  "StatusMessage": "IPSEC IS DOWN"
              }
          ],
          "State": "available",
          "VpnGatewayId": "vgw-9a4cacf3",
          "CustomerGatewayId": "cgw-0e11f167"
          "Type": "ipsec.1"
      }
  }
  
**To describe your available VPN connections**

This example describes your VPN connections with a state of ``available``.

Command::

  aws ec2 describe-vpn-connections --filters "Name=state,Values=available"


======
Output
======

VpnConnections -> (list)

  

  Information about one or more VPN connections.

  

  (structure)

    

    Describes a VPN connection.

    

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
