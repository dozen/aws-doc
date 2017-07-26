[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect describe-lags:


*************
describe-lags
*************



===========
Description
===========



Describes the link aggregation groups (LAGs) in your account. 

 

If a LAG ID is provided, only information about the specified LAG is returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/DescribeLags>`_


========
Synopsis
========

::

    describe-lags
  [--lag-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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

**To describe your LAGs**

The following command describes all of your LAGs for the current region.

Command::

  aws directconnect describe-lags

Output::

  {
    "lags": [
        {
            "awsDevice": "EqDC2-19y7z3m17xpuz", 
            "numberOfConnections": 2, 
            "lagState": "down", 
            "ownerAccount": "123456789012", 
            "lagName": "DA-LAG", 
            "connections": [
                {
                    "ownerAccount": "123456789012", 
                    "connectionId": "dxcon-ffnikghc", 
                    "lagId": "dxlag-fgsu9erb", 
                    "connectionState": "requested", 
                    "bandwidth": "10Gbps", 
                    "location": "EqDC2", 
                    "connectionName": "Requested Connection 1 for Lag dxlag-fgsu9erb", 
                    "region": "us-east-1"
                }, 
                {
                    "ownerAccount": "123456789012", 
                    "connectionId": "dxcon-fglgbdea", 
                    "lagId": "dxlag-fgsu9erb", 
                    "connectionState": "requested", 
                    "bandwidth": "10Gbps", 
                    "location": "EqDC2", 
                    "connectionName": "Requested Connection 2 for Lag dxlag-fgsu9erb", 
                    "region": "us-east-1"
                }
            ], 
            "lagId": "dxlag-fgsu9erb", 
            "minimumLinks": 0, 
            "connectionsBandwidth": "10Gbps", 
            "region": "us-east-1", 
            "location": "EqDC2"
        }
    ]
  }

======
Output
======

lags -> (list)

  

  A list of LAGs.

  

  (structure)

    

    Describes a link aggregation group (LAG). A LAG is a connection that uses the Link Aggregation Control Protocol (LACP) to logically aggregate a bundle of physical connections. Like an interconnect, it can host other connections. All connections in a LAG must terminate on the same physical AWS Direct Connect endpoint, and must be the same bandwidth.

    

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

          

          

        

      

    allowsHostedConnections -> (boolean)

      

      Indicates whether the LAG can host other connections.

       

      .. note::

         

        This is intended for use by AWS Direct Connect partners only.

         

      

      

    

  

