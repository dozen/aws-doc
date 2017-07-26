[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect create-private-virtual-interface:


********************************
create-private-virtual-interface
********************************



===========
Description
===========



Creates a new private virtual interface. A virtual interface is the VLAN that transports AWS Direct Connect traffic. A private virtual interface supports sending traffic to a single virtual private cloud (VPC).



========
Synopsis
========

::

    create-private-virtual-interface
  --connection-id <value>
  --new-private-virtual-interface <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--connection-id`` (string)


  ID of the connection.

   

  Example: dxcon-fg5678gh

   

  Default: None

  

``--new-private-virtual-interface`` (structure)


  Detailed information for the private virtual interface to be created.

   

  Default: None

  



Shorthand Syntax::

    virtualInterfaceName=string,vlan=integer,asn=integer,authKey=string,amazonAddress=string,customerAddress=string,virtualGatewayId=string




JSON Syntax::

  {
    "virtualInterfaceName": "string",
    "vlan": integer,
    "asn": integer,
    "authKey": "string",
    "amazonAddress": "string",
    "customerAddress": "string",
    "virtualGatewayId": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ownerAccount -> (string)

  

  

virtualInterfaceId -> (string)

  

  ID of the virtual interface.

   

  Example: dxvif-123dfg56

   

  Default: None

  

  

location -> (string)

  

  Where the connection is located.

   

  Example: EqSV5

   

  Default: None

  

  

connectionId -> (string)

  

  ID of the connection.

   

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

  

  Autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.

   

  Example: 65000

  

  

authKey -> (string)

  

  Authentication key for BGP configuration.

   

  Example: asdf34example

  

  

amazonAddress -> (string)

  

  IP address assigned to the Amazon interface.

   

  Example: 192.168.1.1/30

  

  

customerAddress -> (string)

  

  IP address assigned to the customer interface.

   

  Example: 192.168.1.2/30

  

  

virtualInterfaceState -> (string)

  State of the virtual interface. 

   
  * **Confirming** : The creation of the virtual interface is pending confirmation from the virtual interface owner. If the owner of the virtual interface is different from the owner of the connection on which it is provisioned, then the virtual interface will remain in this state until it is confirmed by the virtual interface owner.
   
  * **Verifying** : This state only applies to public virtual interfaces. Each public virtual interface needs validation before the virtual interface can be created.
   
  * **Pending** : A virtual interface is in this state from the time that it is created until the virtual interface is ready to forward traffic.
   
  * **Available** : A virtual interface that is able to forward traffic.
   
  * **Down** : A virtual interface that is BGP down.
   
  * **Deleting** : A virtual interface is in this state immediately after calling *delete-virtual-interface* until it can no longer forward traffic.
   
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

       

      Example: 10.10.10.0/24,10.10.11.0/24

      

      

    

  

