[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect describe-hosted-connections:


***************************
describe-hosted-connections
***************************



===========
Description
===========



Returns a list of hosted connections that have been provisioned on the given interconnect or link aggregation group (LAG).

 

.. note::

   

  This is intended for use by AWS Direct Connect partners only.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/DescribeHostedConnections>`_


========
Synopsis
========

::

    describe-hosted-connections
  --connection-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--connection-id`` (string)


  The ID of the interconnect or LAG on which the hosted connections are provisioned.

   

  Example: dxcon-abc123 or dxlag-abc123

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list connections on an interconnect**

The following example lists connections that have been provisioned on the given interconnect.

Command::

  aws directconnect describe-hosted-connections --connection-id dxcon-fgktov66

Output::

  {
      "connections": [
          {
              "partnerName": "TIVIT", 
              "vlan": 101, 
              "ownerAccount": "123456789012", 
              "connectionId": "dxcon-ffzc51m1", 
              "connectionState": "ordering", 
              "bandwidth": "500Mbps", 
              "location": "TIVIT", 
              "connectionName": "mydcinterconnect", 
              "region": "sa-east-1"
          }
      ]
  }

======
Output
======

connections -> (list)

  

  A list of connections.

  

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

      

      

    

  

