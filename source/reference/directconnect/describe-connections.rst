[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect describe-connections:


********************
describe-connections
********************



===========
Description
===========



Displays all connections in this region.

 

If a connection ID is provided, the call returns only that particular connection.



========
Synopsis
========

::

    describe-connections
  [--connection-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--connection-id`` (string)


  ID of the connection.

   

  Example: dxcon-fg5678gh

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

connections -> (list)

  

  A list of connections.

  

  (structure)

    

    A connection represents the physical network connection between the AWS Direct Connect location and the customer.

    

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

      

      Bandwidth of the connection.

       

      Example: 1Gbps (for regular connections), or 500Mbps (for hosted connections)

       

      Default: None

      

      

    vlan -> (integer)

      

      The VLAN ID.

       

      Example: 101

      

      

    partnerName -> (string)

      

      

    

  

