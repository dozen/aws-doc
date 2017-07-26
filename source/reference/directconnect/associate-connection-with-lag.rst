[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect associate-connection-with-lag:


*****************************
associate-connection-with-lag
*****************************



===========
Description
===========



Associates an existing connection with a link aggregation group (LAG). The connection is interrupted and re-established as a member of the LAG (connectivity to AWS will be interrupted). The connection must be hosted on the same AWS Direct Connect endpoint as the LAG, and its bandwidth must match the bandwidth for the LAG. You can reassociate a connection that's currently associated with a different LAG; however, if removing the connection will cause the original LAG to fall below its setting for minimum number of operational connections, the request fails.

 

Any virtual interfaces that are directly associated with the connection are automatically re-associated with the LAG. If the connection was originally associated with a different LAG, the virtual interfaces remain associated with the original LAG.

 

For interconnects, any hosted connections are automatically re-associated with the LAG. If the interconnect was originally associated with a different LAG, the hosted connections remain associated with the original LAG.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/AssociateConnectionWithLag>`_


========
Synopsis
========

::

    associate-connection-with-lag
  --connection-id <value>
  --lag-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--connection-id`` (string)


  The ID of the connection.

   

  Example: dxcon-abc123

   

  Default: None

  

``--lag-id`` (string)


  The ID of the LAG with which to associate the connection.

   

  Example: dxlag-abc123

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To associate a connection with a LAG**

The following example associates the specified connection with the specified LAG.

Command::

  aws directconnect associate-connection-with-lag --lag-id dxlag-fhccu14t --connection-id dxcon-fg9607vm

Output::

  {
    "ownerAccount": "123456789012", 
    "connectionId": "dxcon-fg9607vm", 
    "lagId": "dxlag-fhccu14t", 
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

  

  

