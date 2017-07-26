[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect create-interconnect:


*******************
create-interconnect
*******************



===========
Description
===========



Creates a new interconnect between a AWS Direct Connect partner's network and a specific AWS Direct Connect location.

 

An interconnect is a connection which is capable of hosting other connections. The AWS Direct Connect partner can use an interconnect to provide sub-1Gbps AWS Direct Connect service to tier 2 customers who do not have their own connections. Like a standard connection, an interconnect links the AWS Direct Connect partner's network to an AWS Direct Connect location over a standard 1 Gbps or 10 Gbps Ethernet fiber-optic cable. One end is connected to the partner's router, the other to an AWS Direct Connect router.

 

For each end customer, the AWS Direct Connect partner provisions a connection on their interconnect by calling AllocateConnectionOnInterconnect. The end customer can then connect to AWS resources by creating a virtual interface on their connection, using the VLAN assigned to them by the AWS Direct Connect partner.



========
Synopsis
========

::

    create-interconnect
  --interconnect-name <value>
  --bandwidth <value>
  --location <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--interconnect-name`` (string)


  The name of the interconnect.

   

  Example: "*1G Interconnect to AWS* "

   

  Default: None

  

``--bandwidth`` (string)


  The port bandwidth

   

  Example: 1Gbps

   

  Default: None

   

  Available values: 1Gbps,10Gbps

  

``--location`` (string)


  Where the interconnect is located

   

  Example: EqSV5

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

interconnectId -> (string)

  

  The ID of the interconnect.

   

  Example: dxcon-abc123

  

  

interconnectName -> (string)

  

  The name of the interconnect.

   

  Example: "*1G Interconnect to AWS* "

  

  

interconnectState -> (string)

  State of the interconnect. 

   
  * **Requested** : The initial state of an interconnect. The interconnect stays in the requested state until the Letter of Authorization (LOA) is sent to the customer.
   
  * **Pending** : The interconnect has been approved, and is being initialized.
   
  * **Available** : The network link is up, and the interconnect is ready for use.
   
  * **Down** : The network link is down.
   
  * **Deleting** : The interconnect is in the process of being deleted.
   
  * **Deleted** : The interconnect has been deleted.
   

  

  

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

   

  Example: 1Gbps

   

  Default: None

  

  

