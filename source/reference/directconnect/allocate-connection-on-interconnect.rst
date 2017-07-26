[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect allocate-connection-on-interconnect:


***********************************
allocate-connection-on-interconnect
***********************************



===========
Description
===========



Creates a hosted connection on an interconnect.

 

Allocates a vlan number and a specified amount of bandwidth for use by a hosted connection on the given interconnect.



========
Synopsis
========

::

    allocate-connection-on-interconnect
  --bandwidth <value>
  --connection-name <value>
  --owner-account <value>
  --interconnect-id <value>
  --vlan <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bandwidth`` (string)


  bandwidth of the connection.

   

  Example: "*500Mbps* "

   

  Default: None

  

``--connection-name`` (string)


  Name of the provisioned connection.

   

  Example: "*500M Connection to AWS* "

   

  Default: None

  

``--owner-account`` (string)


  Numeric account Id of the customer for whom the connection will be provisioned.

   

  Example: 123443215678

   

  Default: None

  

``--interconnect-id`` (string)


  ID of the interconnect on which the connection will be provisioned.

   

  Example: dxcon-456abc78

   

  Default: None

  

``--vlan`` (integer)


  The dedicated vlan provisioned to the connection.

   

  Example: 101

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ownerAccount -> (string)

  

  

connectionId -> (string)

  

  ID of the connection.

   

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

  

  The vlan ID.

   

  Example: 101

  

  

partnerName -> (string)

  

  

