[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect create-connection:


*****************
create-connection
*****************



===========
Description
===========



Creates a new connection between the customer network and a specific AWS Direct Connect location.

 

A connection links your internal network to an AWS Direct Connect location over a standard 1 gigabit or 10 gigabit Ethernet fiber-optic cable. One end of the cable is connected to your router, the other to an AWS Direct Connect router. An AWS Direct Connect location provides access to Amazon Web Services in the region it is associated with. You can establish connections with AWS Direct Connect locations in multiple regions, but a connection in one region does not provide connectivity to other regions.

 

You can automatically add the new connection to a link aggregation group (LAG) by specifying a LAG ID in the request. This ensures that the new connection is allocated on the same AWS Direct Connect endpoint that hosts the specified LAG. If there are no available ports on the endpoint, the request fails and no connection will be created.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/CreateConnection>`_


========
Synopsis
========

::

    create-connection
  --location <value>
  --bandwidth <value>
  --connection-name <value>
  [--lag-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--location`` (string)


  Where the connection is located.

   

  Example: EqSV5

   

  Default: None

  

``--bandwidth`` (string)


  bandwidth of the connection.

   

  Example: 1Gbps

   

  Default: None

  

``--connection-name`` (string)


  The name of the connection.

   

  Example: "*My Connection to AWS* "

   

  Default: None

  

``--lag-id`` (string)


  The ID of the LAG.

   

  Example: dxlag-fg5678gh

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a connection from your network to an AWS Direct Connect location**

The following ``create-connection`` command creates a connection from your network to an AWS Direct Connect location::

  aws directconnect create-connection --location TIVIT --bandwidth 1Gbps --connection-name "Connection to AWS"

Output::

  {
      "ownerAccount": "123456789012", 
      "connectionId": "dxcon-fg31dyv6", 
      "connectionState": "requested", 
      "bandwidth": "1Gbps", 
      "location": "TIVIT", 
      "connectionName": "Connection to AWS", 
      "region": "sa-east-1"
  }

======
Output
======

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

  

  bandwidth of the connection.

   

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

  

  

