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

 

You can automatically add the new interconnect to a link aggregation group (LAG) by specifying a LAG ID in the request. This ensures that the new interconnect is allocated on the same AWS Direct Connect endpoint that hosts the specified LAG. If there are no available ports on the endpoint, the request fails and no interconnect will be created.

 

For each end customer, the AWS Direct Connect partner provisions a connection on their interconnect by calling AllocateConnectionOnInterconnect. The end customer can then connect to AWS resources by creating a virtual interface on their connection, using the VLAN assigned to them by the AWS Direct Connect partner.

 

.. note::

   

  This is intended for use by AWS Direct Connect partners only.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/CreateInterconnect>`_


========
Synopsis
========

::

    create-interconnect
  --interconnect-name <value>
  --bandwidth <value>
  --location <value>
  [--lag-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

**To create an interconnect between a partner's network and AWS**

The following ``create-interconnect`` command creates an interconnect between an AWS Direct Connect partner's network and a specific AWS Direct Connect location::

  aws directconnect create-interconnect --interconnect-name "1G Interconnect to AWS" --bandwidth 1Gbps --location TIVIT

Output::

  {
      "region": "sa-east-1", 
      "bandwidth": "1Gbps", 
      "location": "TIVIT", 
      "interconnectName": "1G Interconnect to AWS", 
      "interconnectId": "dxcon-fgktov66", 
      "interconnectState": "requested"
  }

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

  

  

loaIssueTime -> (timestamp)

  

  The time of the most recent call to describe-interconnect-loa for this Interconnect.

  

  

lagId -> (string)

  

  The ID of the LAG.

   

  Example: dxlag-fg5678gh

  

  

awsDevice -> (string)

  

  The Direct Connection endpoint which the physical connection terminates on.

  

  

