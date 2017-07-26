[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect create-lag:


**********
create-lag
**********



===========
Description
===========



Creates a new link aggregation group (LAG) with the specified number of bundled physical connections between the customer network and a specific AWS Direct Connect location. A LAG is a logical interface that uses the Link Aggregation Control Protocol (LACP) to aggregate multiple 1 gigabit or 10 gigabit interfaces, allowing you to treat them as a single interface.

 

All connections in a LAG must use the same bandwidth (for example, 10 Gbps), and must terminate at the same AWS Direct Connect endpoint.

 

You can have up to 10 connections per LAG. Regardless of this limit, if you request more connections for the LAG than AWS Direct Connect can allocate on a single endpoint, no LAG is created.

 

You can specify an existing physical connection or interconnect to include in the LAG (which counts towards the total number of connections). Doing so interrupts the current physical connection or hosted connections, and re-establishes them as a member of the LAG. The LAG will be created on the same AWS Direct Connect endpoint to which the connection terminates. Any virtual interfaces associated with the connection are automatically disassociated and re-associated with the LAG. The connection ID does not change.

 

If the AWS account used to create a LAG is a registered AWS Direct Connect partner, the LAG is automatically enabled to host sub-connections. For a LAG owned by a partner, any associated virtual interfaces cannot be directly configured.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/CreateLag>`_


========
Synopsis
========

::

    create-lag
  --number-of-connections <value>
  --location <value>
  --connections-bandwidth <value>
  --lag-name <value>
  [--connection-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--number-of-connections`` (integer)


  The number of physical connections initially provisioned and bundled by the LAG.

   

  Default: None

  

``--location`` (string)


  The AWS Direct Connect location in which the LAG should be allocated.

   

  Example: EqSV5

   

  Default: None

  

``--connections-bandwidth`` (string)


  The bandwidth of the individual physical connections bundled by the LAG.

   

  Default: None

   

  Available values: 1Gbps, 10Gbps

  

``--lag-name`` (string)


  The name of the LAG.

   

  Example: "``3x10G LAG to AWS`` "

   

  Default: None

  

``--connection-id`` (string)


  The ID of an existing connection to migrate to the LAG.

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a LAG with new connections**

The following example creates a LAG and requests two new AWS Direct Connect connections for the LAG with a bandwidth of 1 Gbps.

Command::

  aws directconnect create-lag --location CSVA1 --number-of-connections 2 --connections-bandwidth 1Gbps --lag-name 1GBLag

Output::

  {
    "awsDevice": "CSVA1-23u8tlpaz8iks", 
    "numberOfConnections": 2, 
    "lagState": "pending", 
    "ownerAccount": "123456789012", 
    "lagName": "1GBLag", 
    "connections": [
        {
            "ownerAccount": "123456789012", 
            "connectionId": "dxcon-ffqr6x5q", 
            "lagId": "dxlag-ffjhj9lx", 
            "connectionState": "requested", 
            "bandwidth": "1Gbps", 
            "location": "CSVA1", 
            "connectionName": "Requested Connection 1 for Lag dxlag-ffjhj9lx", 
            "region": "us-east-1"
        }, 
        {
            "ownerAccount": "123456789012", 
            "connectionId": "dxcon-fflqyj95", 
            "lagId": "dxlag-ffjhj9lx", 
            "connectionState": "requested", 
            "bandwidth": "1Gbps", 
            "location": "CSVA1", 
            "connectionName": "Requested Connection 2 for Lag dxlag-ffjhj9lx", 
            "region": "us-east-1"
        }
    ], 
    "lagId": "dxlag-ffjhj9lx", 
    "minimumLinks": 0, 
    "connectionsBandwidth": "1Gbps", 
    "region": "us-east-1", 
    "location": "CSVA1"
  }

**To create a LAG using an existing connection**

The following example creates a LAG from an existing connection in your account, and requests a second new connection for the LAG with the same bandwidth and location as the existing connection. 

Command::

  aws directconnect create-lag --location EqDC2 --number-of-connections 2 --connections-bandwidth 1Gbps --lag-name 2ConnLAG --connection-id dxcon-fgk145dr

Output::

  {
    "awsDevice": "EqDC2-4h6ce2r1bes6", 
    "numberOfConnections": 2, 
    "lagState": "pending", 
    "ownerAccount": "123456789012", 
    "lagName": "2ConnLAG", 
    "connections": [
        {
            "ownerAccount": "123456789012", 
            "connectionId": "dxcon-fh6ljcvo", 
            "lagId": "dxlag-fhccu14t", 
            "connectionState": "requested", 
            "bandwidth": "1Gbps", 
            "location": "EqDC2", 
            "connectionName": "Requested Connection 1 for Lag dxlag-fhccu14t", 
            "region": "us-east-1"
        }, 
        {
            "ownerAccount": "123456789012", 
            "connectionId": "dxcon-fgk145dr", 
            "lagId": "dxlag-fhccu14t", 
            "connectionState": "down", 
            "bandwidth": "1Gbps", 
            "location": "EqDC2", 
            "connectionName": "VAConn1", 
            "region": "us-east-1"
        }
    ], 
    "lagId": "dxlag-fhccu14t", 
    "minimumLinks": 0, 
    "connectionsBandwidth": "1Gbps", 
    "region": "us-east-1", 
    "location": "EqDC2"
  }

======
Output
======

connectionsBandwidth -> (string)

  

  The individual bandwidth of the physical connections bundled by the LAG.

   

  Available values: 1Gbps, 10Gbps

  

  

numberOfConnections -> (integer)

  

  The number of physical connections bundled by the LAG, up to a maximum of 10.

  

  

lagId -> (string)

  

  The ID of the LAG.

   

  Example: dxlag-fg5678gh

  

  

ownerAccount -> (string)

  

  The owner of the LAG.

  

  

lagName -> (string)

  

  The name of the LAG.

  

  

lagState -> (string)

  

  The state of the LAG.

   

   
  * **Requested** : The initial state of a LAG. The LAG stays in the requested state until the Letter of Authorization (LOA) is available. 
   
  * **Pending** : The LAG has been approved, and is being initialized. 
   
  * **Available** : The network link is established, and the LAG is ready for use. 
   
  * **Down** : The network link is down. 
   
  * **Deleting** : The LAG is in the process of being deleted. 
   
  * **Deleted** : The LAG has been deleted. 
   

  

  

location -> (string)

  

  Where the connection is located.

   

  Example: EqSV5

   

  Default: None

  

  

region -> (string)

  

  The AWS region where the connection is located.

   

  Example: us-east-1

   

  Default: None

  

  

minimumLinks -> (integer)

  

  The minimum number of physical connections that must be operational for the LAG itself to be operational. If the number of operational connections drops below this setting, the LAG state changes to ``down`` . This value can help to ensure that a LAG is not overutilized if a significant number of its bundled connections go down.

  

  

awsDevice -> (string)

  

  The AWS Direct Connection endpoint that hosts the LAG.

  

  

connections -> (list)

  

  A list of connections bundled by this LAG.

  

  (structure)

    

    A connection represents the physical network connection between the AWS Direct Connect location and the customer.

    

    ownerAccount -> (string)

      

      The AWS account that will own the new connection.

      

      

    connectionId -> (string)

      

      The ID of the connection. This field is also used as the ID type for operations that use multiple connection types (LAG, interconnect, and/or connection).

       

      Example: dxcon-fg5678gh

       

      Default: None

      

      

    connectionName -> (string)

      

      The name of the connection.

       

      Example: "*My Connection to AWS* "

       

      Default: None

      

      

    connectionState -> (string)

      

      State of the connection.

       

       
      * **Ordering** : The initial state of a hosted connection provisioned on an interconnect. The connection stays in the ordering state until the owner of the hosted connection confirms or declines the connection order. 
       
      * **Requested** : The initial state of a standard connection. The connection stays in the requested state until the Letter of Authorization (LOA) is sent to the customer. 
       
      * **Pending** : The connection has been approved, and is being initialized. 
       
      * **Available** : The network link is up, and the connection is ready for use. 
       
      * **Down** : The network link is down. 
       
      * **Deleting** : The connection is in the process of being deleted. 
       
      * **Deleted** : The connection has been deleted. 
       
      * **Rejected** : A hosted connection in the 'Ordering' state will enter the 'Rejected' state if it is deleted by the end customer. 
       

      

      

    region -> (string)

      

      The AWS region where the connection is located.

       

      Example: us-east-1

       

      Default: None

      

      

    location -> (string)

      

      Where the connection is located.

       

      Example: EqSV5

       

      Default: None

      

      

    bandwidth -> (string)

      

      connections-bandwidth of the connection.

       

      Example: 1Gbps (for regular connections), or 500Mbps (for hosted connections)

       

      Default: None

      

      

    vlan -> (integer)

      

      The VLAN ID.

       

      Example: 101

      

      

    partnerName -> (string)

      

      The name of the AWS Direct Connect service provider associated with the connection.

      

      

    loaIssueTime -> (timestamp)

      

      The time of the most recent call to  describe-loa for this connection.

      

      

    lagId -> (string)

      

      The ID of the LAG.

       

      Example: dxlag-fg5678gh

      

      

    awsDevice -> (string)

      

      The Direct Connection endpoint which the physical connection terminates on.

      

      

    

  

allowsHostedConnections -> (boolean)

  

  Indicates whether the LAG can host other connections.

   

  .. note::

     

    This is intended for use by AWS Direct Connect partners only.

     

  

  

