[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect disassociate-connection-from-lag:


********************************
disassociate-connection-from-lag
********************************



===========
Description
===========



Disassociates a connection from a link aggregation group (LAG). The connection is interrupted and re-established as a standalone connection (the connection is not deleted; to delete the connection, use the  delete-connection request). If the LAG has associated virtual interfaces or hosted connections, they remain associated with the LAG. A disassociated connection owned by an AWS Direct Connect partner is automatically converted to an interconnect.

 

If disassociating the connection will cause the LAG to fall below its setting for minimum number of operational connections, the request fails, except when it's the last member of the LAG. If all connections are disassociated, the LAG continues to exist as an empty LAG with no physical connections. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/DisassociateConnectionFromLag>`_


========
Synopsis
========

::

    disassociate-connection-from-lag
  --connection-id <value>
  --lag-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--connection-id`` (string)


  The ID of the connection to disassociate from the LAG.

   

  Example: dxcon-abc123

   

  Default: None

  

``--lag-id`` (string)


  The ID of the LAG.

   

  Example: dxlag-abc123

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To disassociate a connection from a LAG**

The following example disassociates the specified connection from the specified LAG.

Command::

  aws directconnect disassociate-connection-from-lag --lag-id dxlag-fhccu14t --connection-id  dxcon-fg9607vm

Output::

  {
    "ownerAccount": "123456789012", 
    "connectionId": "dxcon-fg9607vm", 
    "connectionState": "requested", 
    "bandwidth": "1Gbps", 
    "location": "EqDC2", 
    "connectionName": "Con2ForLag", 
    "region": "us-east-1"
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

  

  Bandwidth of the connection.

   

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

  

  

