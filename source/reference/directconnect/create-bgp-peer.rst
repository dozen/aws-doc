[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect create-bgp-peer:


***************
create-bgp-peer
***************



===========
Description
===========



Creates a new BGP peer on a specified virtual interface. The BGP peer cannot be in the same address family (IPv4/IPv6) of an existing BGP peer on the virtual interface.

 

You must create a BGP peer for the corresponding address family in order to access AWS resources that also use that address family.

 

When creating a IPv6 BGP peer, the Amazon address and customer address fields must be left blank. IPv6 addresses are automatically assigned from Amazon's pool of IPv6 addresses; you cannot specify custom IPv6 addresses.

 

For a public virtual interface, the Autonomous System Number (ASN) must be private or already whitelisted for the virtual interface.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/CreateBGPPeer>`_


========
Synopsis
========

::

    create-bgp-peer
  [--virtual-interface-id <value>]
  [--new-bgp-peer <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--virtual-interface-id`` (string)


  The ID of the virtual interface on which the BGP peer will be provisioned.

   

  Example: dxvif-456abc78

   

  Default: None

  

``--new-bgp-peer`` (structure)


  Detailed information for the BGP peer to be created.

   

  Default: None

  



Shorthand Syntax::

    asn=integer,authKey=string,addressFamily=string,amazonAddress=string,customerAddress=string




JSON Syntax::

  {
    "asn": integer,
    "authKey": "string",
    "addressFamily": "ipv4"|"ipv6",
    "amazonAddress": "string",
    "customerAddress": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an IPv6 BGP peering session**

The following example creates an IPv6 BGP peering session on private virtual interface ``dxvif-fg1vuj3d``. The peer IPv6 addresses are automatically allocated by Amazon.

Command::

  aws directconnect create-bgp-peer --virtual-interface-id dxvif-fg1vuj3d --new-bgp-peer asn=64600,addressFamily=ipv6
  
Output::

  {
    "virtualInterface": {
        "virtualInterfaceState": "available", 
        "asn": 65000, 
        "vlan": 125, 
        "customerAddress": "169.254.255.2/30", 
        "ownerAccount": "123456789012", 
        "connectionId": "dxcon-fguhmqlc", 
        "addressFamily": "ipv4", 
        "virtualGatewayId": "vgw-f9eb0c90", 
        "virtualInterfaceId": "dxvif-fg1vuj3d", 
        "authKey": "0xC_ukbCerl6EYA0example", 
        "routeFilterPrefixes": [], 
        "location": "EqDC2", 
        "bgpPeers": [
            {
                "bgpStatus": "down", 
                "customerAddress": "169.254.255.2/30", 
                "addressFamily": "ipv4", 
                "authKey": "0xC_ukbCerl6EYA0uexample", 
                "bgpPeerState": "available", 
                "amazonAddress": "169.254.255.1/30", 
                "asn": 65000
            }, 
            {
                "bgpStatus": "down", 
                "customerAddress": "2001:db8:1100:2f0:0:1:9cb4:4216/125", 
                "addressFamily": "ipv6", 
                "authKey": "0xS27kAIU_VHPjjAexample", 
                "bgpPeerState": "pending", 
                "amazonAddress": "2001:db8:1100:2f0:0:1:9cb4:4211/125", 
                "asn": 64600
            }
        ], 
        "customerRouterConfig": "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<logical_connection id=\"dxvif-fg1vuj3d\">\n  <vlan>125</vlan>\n  <customer_address>169.254.255.2/30</customer_address>\n  <amazon_address>169.254.255.1/30</amazon_address>\n  <bgp_asn>65000</bgp_asn>\n  <bgp_auth_key>0xC_ukbCerl6EYA0uexample</bgp_auth_key>\n  <ipv6_customer_address>2001:db8:1100:2f0:0:1:9cb4:4216/125</ipv6_customer_address>\n  <ipv6_amazon_address>2001:db8:1100:2f0:0:1:9cb4:4211/125</ipv6_amazon_address>\n  <ipv6_bgp_asn>64600</ipv6_bgp_asn>\n  <ipv6_bgp_auth_key>0xS27kAIU_VHPjjAexample</ipv6_bgp_auth_key>\n  <amazon_bgp_asn>7224</amazon_bgp_asn>\n  <connection_type>private</connection_type>\n</logical_connection>\n", 
        "amazonAddress": "169.254.255.1/30", 
        "virtualInterfaceType": "private", 
        "virtualInterfaceName": "Test"
    }
  }

======
Output
======

virtualInterface -> (structure)

  

  A virtual interface (VLAN) transmits the traffic between the AWS Direct Connect location and the customer.

  

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
         

        

        

      

    

  

