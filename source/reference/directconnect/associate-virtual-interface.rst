[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect associate-virtual-interface:


***************************
associate-virtual-interface
***************************



===========
Description
===========



Associates a virtual interface with a specified link aggregation group (LAG) or connection. Connectivity to AWS is temporarily interrupted as the virtual interface is being migrated. If the target connection or LAG has an associated virtual interface with a conflicting VLAN number or a conflicting IP address, the operation fails. 

 

Virtual interfaces associated with a hosted connection cannot be associated with a LAG; hosted connections must be migrated along with their virtual interfaces using  associate-hosted-connection .

 

Hosted virtual interfaces (an interface for which the owner of the connection is not the owner of physical connection) can only be reassociated by the owner of the physical connection.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/AssociateVirtualInterface>`_


========
Synopsis
========

::

    associate-virtual-interface
  --virtual-interface-id <value>
  --connection-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--virtual-interface-id`` (string)


  The ID of the virtual interface.

   

  Example: dxvif-123dfg56

   

  Default: None

  

``--connection-id`` (string)


  The ID of the LAG or connection with which to associate the virtual interface.

   

  Example: dxlag-abc123 or dxcon-abc123

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To associate a virtual interface with a connection**

The following example associates the specified virtual interface with the specified LAG. Alternatively, to associate the virtual interface with a connection, specify the ID of an AWS Direct Connect connection for ``--connection-id``; for example, ``dxcon-ffnikghc``.

Command::

  aws directconnect associate-virtual-interface --connection-id dxlag-ffjhj9lx --virtual-interface-id dxvif-fgputw0j
  
Output::

  {
    "virtualInterfaceState": "pending", 
    "asn": 65000, 
    "vlan": 123, 
    "customerAddress": "169.254.255.2/30", 
    "ownerAccount": "123456789012", 
    "connectionId": "dxlag-ffjhj9lx", 
    "addressFamily": "ipv4", 
    "virtualGatewayId": "vgw-38e90b51", 
    "virtualInterfaceId": "dxvif-fgputw0j", 
    "authKey": "0x123pK5_VBqv.UQ3kJ4123_", 
    "routeFilterPrefixes": [], 
    "location": "CSVA1", 
    "bgpPeers": [
        {
            "bgpStatus": "down", 
            "customerAddress": "169.254.255.2/30", 
            "addressFamily": "ipv4", 
            "authKey": "0x123pK5_VBqv.UQ3kJ4123_", 
            "bgpPeerState": "deleting", 
            "amazonAddress": "169.254.255.1/30", 
            "asn": 65000
        }, 
        {
            "bgpStatus": "down", 
            "customerAddress": "169.254.255.2/30", 
            "addressFamily": "ipv4", 
            "authKey": "0x123pK5_VBqv.UQ3kJ4123_", 
            "bgpPeerState": "pending", 
            "amazonAddress": "169.254.255.1/30", 
            "asn": 65000
        }
    ], 
    "customerRouterConfig": "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<logical_connection id=\"dxvif-fgputw0j\">\n  <vlan>123</vlan>\n  <customer_address>169.254.255.2/30</customer_address>\n  <amazon_address>169.254.255.1/30</amazon_address>\n  <bgp_asn>65000</bgp_asn>\n  <bgp_auth_key>0x123pK5_VBqv.UQ3kJ4123_</bgp_auth_key>\n  <amazon_bgp_asn>7224</amazon_bgp_asn>\n  <connection_type>private</connection_type>\n</logical_connection>\n", 
    "amazonAddress": "169.254.255.1/30", 
    "virtualInterfaceType": "private", 
    "virtualInterfaceName": "VIF1A"
  }

======
Output
======

ownerAccount -> (string)

  

  The AWS account that will own the new virtual interface.

  

  

virtualInterfaceId -> (string)

  

  The ID of the virtual interface.

   

  Example: dxvif-123dfg56

   

  Default: None

  

  

location -> (string)

  

  Where the connection is located.

   

  Example: EqSV5

   

  Default: None

  

  

connectionId -> (string)

  

  The ID of the connection. This field is also used as the ID type for operations that use multiple connection types (LAG, interconnect, and/or connection).

   

  Example: dxcon-fg5678gh

   

  Default: None

  

  

virtualInterfaceType -> (string)

  

  The type of virtual interface.

   

  Example: private (Amazon VPC) or public (Amazon S3, Amazon DynamoDB, and so on.)

  

  

virtualInterfaceName -> (string)

  

  The name of the virtual interface assigned by the customer.

   

  Example: "My VPC"

  

  

vlan -> (integer)

  

  The VLAN ID.

   

  Example: 101

  

  

asn -> (integer)

  

  The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.

   

  Example: 65000

  

  

authKey -> (string)

  

  The authentication key for BGP configuration.

   

  Example: asdf34example

  

  

amazonAddress -> (string)

  

  IP address assigned to the Amazon interface.

   

  Example: 192.168.1.1/30 or 2001:db8::1/125

  

  

customerAddress -> (string)

  

  IP address assigned to the customer interface.

   

  Example: 192.168.1.2/30 or 2001:db8::2/125

  

  

addressFamily -> (string)

  

  Indicates the address family for the BGP peer.

   

   
  * **ipv4** : IPv4 address family 
   
  * **ipv6** : IPv6 address family 
   

  

  

virtualInterfaceState -> (string)

  

  State of the virtual interface.

   

   
  * **Confirming** : The creation of the virtual interface is pending confirmation from the virtual interface owner. If the owner of the virtual interface is different from the owner of the connection on which it is provisioned, then the virtual interface will remain in this state until it is confirmed by the virtual interface owner. 
   
  * **Verifying** : This state only applies to public virtual interfaces. Each public virtual interface needs validation before the virtual interface can be created. 
   
  * **Pending** : A virtual interface is in this state from the time that it is created until the virtual interface is ready to forward traffic. 
   
  * **Available** : A virtual interface that is able to forward traffic. 
   
  * **Down** : A virtual interface that is BGP down. 
   
  * **Deleting** : A virtual interface is in this state immediately after calling  delete-virtual-interface until it can no longer forward traffic. 
   
  * **Deleted** : A virtual interface that cannot forward traffic. 
   
  * **Rejected** : The virtual interface owner has declined creation of the virtual interface. If a virtual interface in the 'Confirming' state is deleted by the virtual interface owner, the virtual interface will enter the 'Rejected' state. 
   

  

  

customerRouterConfig -> (string)

  

  Information for generating the customer router configuration.

  

  

virtualGatewayId -> (string)

  

  The ID of the virtual private gateway to a VPC. This only applies to private virtual interfaces.

   

  Example: vgw-123er56

  

  

routeFilterPrefixes -> (list)

  

  A list of routes to be advertised to the AWS network in this region (public virtual interface).

  

  (structure)

    

    A route filter prefix that the customer can advertise through Border Gateway Protocol (BGP) over a public virtual interface.

    

    cidr -> (string)

      

      CIDR notation for the advertised route. Multiple routes are separated by commas.

       

      IPv6 CIDRs must be at least a /64 or shorter

       

      Example: 10.10.10.0/24,10.10.11.0/24,2001:db8::/64

      

      

    

  

bgpPeers -> (list)

  

  A list of the BGP peers configured on this virtual interface.

  

  (structure)

    

    A structure containing information about a BGP peer.

    

    asn -> (integer)

      

      The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.

       

      Example: 65000

      

      

    authKey -> (string)

      

      The authentication key for BGP configuration.

       

      Example: asdf34example

      

      

    addressFamily -> (string)

      

      Indicates the address family for the BGP peer.

       

       
      * **ipv4** : IPv4 address family 
       
      * **ipv6** : IPv6 address family 
       

      

      

    amazonAddress -> (string)

      

      IP address assigned to the Amazon interface.

       

      Example: 192.168.1.1/30 or 2001:db8::1/125

      

      

    customerAddress -> (string)

      

      IP address assigned to the customer interface.

       

      Example: 192.168.1.2/30 or 2001:db8::2/125

      

      

    bgpPeerState -> (string)

      

      The state of the BGP peer.

       

       
      * **Verifying** : The BGP peering addresses or ASN require validation before the BGP peer can be created. This state only applies to BGP peers on a public virtual interface.  
       
      * **Pending** : The BGP peer has been created, and is in this state until it is ready to be established. 
       
      * **Available** : The BGP peer can be established. 
       
      * **Deleting** : The BGP peer is in the process of being deleted. 
       
      * **Deleted** : The BGP peer has been deleted and cannot be established. 
       

      

      

    bgpStatus -> (string)

      

      The Up/Down state of the BGP peer.

       

       
      * **Up** : The BGP peer is established. 
       
      * **Down** : The BGP peer is down. 
       

      

      

    

  

