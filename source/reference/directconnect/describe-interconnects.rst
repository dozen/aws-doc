[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect describe-interconnects:


**********************
describe-interconnects
**********************



===========
Description
===========



Returns a list of interconnects owned by the AWS account.

 

If an interconnect ID is provided, it will only return this particular interconnect.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/DescribeInterconnects>`_


========
Synopsis
========

::

    describe-interconnects
  [--interconnect-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--interconnect-id`` (string)


  The ID of the interconnect.

   

  Example: dxcon-abc123

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list interconnects**

The following ``describe-interconnects`` command lists the interconnects owned by your AWS account::

  aws directconnect describe-interconnects

Output::

  {
      "interconnects": [
          {
              "region": "sa-east-1", 
              "bandwidth": "1Gbps", 
              "location": "TIVIT", 
              "interconnectName": "1G Interconnect to AWS", 
              "interconnectId": "dxcon-fgktov66", 
              "interconnectState": "down"
          }
      ]
  }

======
Output
======

interconnects -> (list)

  

  A list of interconnects.

  

  (structure)

    

    An interconnect is a connection that can host other connections.

     

    Like a standard AWS Direct Connect connection, an interconnect represents the physical connection between an AWS Direct Connect partner's network and a specific Direct Connect location. An AWS Direct Connect partner who owns an interconnect can provision hosted connections on the interconnect for their end customers, thereby providing the end customers with connectivity to AWS services.

     

    The resources of the interconnect, including bandwidth and VLAN numbers, are shared by all of the hosted connections on the interconnect, and the owner of the interconnect determines how these resources are assigned.

    

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

      

      Bandwidth of the connection.

       

      Example: 1Gbps

       

      Default: None

      

      

    loaIssueTime -> (timestamp)

      

      The time of the most recent call to describe-interconnect-loa for this Interconnect.

      

      

    lagId -> (string)

      

      The ID of the LAG.

       

      Example: dxlag-fg5678gh

      

      

    awsDevice -> (string)

      

      The Direct Connection endpoint which the physical connection terminates on.

      

      

    

  

