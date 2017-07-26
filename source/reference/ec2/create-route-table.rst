[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-route-table:


******************
create-route-table
******************



===========
Description
===========



Creates a route table for the specified VPC. After you create a route table, you can add routes and associate the table with a subnet.

 

For more information about route tables, see `Route Tables`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    create-route-table
  [--dry-run | --no-dry-run]
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a route table**

This example creates a route table for the specified VPC.

Command::

  aws ec2 create-route-table --vpc-id vpc-a01106c2

Output::

  {
      "RouteTable": {
          "Associations": [],
          "RouteTableId": "rtb-22574640",
          "VpcId": "vpc-a01106c2",
          "PropagatingVgws": [],
          "Tags": [],
          "Routes": [
              {
                  "GatewayId": "local",
                  "DestinationCidrBlock": "10.0.0.0/16",
                  "State": "active"
              }
          ]
      }  
  }

======
Output
======

RouteTable -> (structure)

  

  Information about the route table.

  

  RouteTableId -> (string)

    

    The ID of the route table.

    

    

  VpcId -> (string)

    

    The ID of the VPC.

    

    

  Routes -> (list)

    

    The routes in the route table.

    

    (structure)

      

      Describes a route in a route table.

      

      DestinationCidrBlock -> (string)

        

        The CIDR block used for the destination match.

        

        

      DestinationPrefixListId -> (string)

        

        The prefix of the AWS service.

        

        

      GatewayId -> (string)

        

        The ID of a gateway attached to your VPC.

        

        

      InstanceId -> (string)

        

        The ID of a NAT instance in your VPC.

        

        

      InstanceOwnerId -> (string)

        

        The AWS account ID of the owner of the instance.

        

        

      NetworkInterfaceId -> (string)

        

        The ID of the network interface.

        

        

      VpcPeeringConnectionId -> (string)

        

        The ID of the VPC peering connection.

        

        

      NatGatewayId -> (string)

        

        The ID of a NAT gateway.

        

        

      State -> (string)

        

        The state of the route. The ``blackhole`` state indicates that the route's target isn't available (for example, the specified gateway isn't attached to the VPC, or the specified NAT instance has been terminated).

        

        

      Origin -> (string)

        

        Describes how the route was created.

         

         
        * ``create-route-table`` indicates that route was automatically created when the route table was created.
         
        * ``create-route`` indicates that the route was manually added to the route table.
         
        * ``enable-vgw-route-propagation`` indicates that the route was propagated by route propagation.
         

        

        

      

    

  Associations -> (list)

    

    The associations between the route table and one or more subnets.

    

    (structure)

      

      Describes an association between a route table and a subnet.

      

      RouteTableAssociationId -> (string)

        

        The ID of the association between a route table and a subnet.

        

        

      RouteTableId -> (string)

        

        The ID of the route table.

        

        

      SubnetId -> (string)

        

        The ID of the subnet. A subnet ID is not returned for an implicit association.

        

        

      Main -> (boolean)

        

        Indicates whether this is the main route table.

        

        

      

    

  Tags -> (list)

    

    Any tags assigned to the route table.

    

    (structure)

      

      Describes a tag.

      

      Key -> (string)

        

        The key of the tag. 

         

        Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

        

        

      Value -> (string)

        

        The value of the tag.

         

        Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

        

        

      

    

  PropagatingVgws -> (list)

    

    Any virtual private gateway (VGW) propagating routes.

    

    (structure)

      

      Describes a virtual private gateway propagating route.

      

      GatewayId -> (string)

        

        The ID of the virtual private gateway (VGW).

        

        

      

    

  



.. _Route Tables: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html
