[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-route-tables:


*********************
describe-route-tables
*********************



===========
Description
===========



Describes one or more of your route tables. 

 

Each subnet in your VPC must be associated with a route table. If a subnet is not explicitly associated with any route table, it is implicitly associated with the main route table. This command does not return the subnet ID for implicit associations.

 

For more information about route tables, see `Route Tables`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    describe-route-tables
  [--dry-run | --no-dry-run]
  [--route-table-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--route-table-ids`` (list)


  One or more route table IDs.

   

  Default: Describes all your route tables.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``association.route-table-association-id`` - The ID of an association ID for the route table. 
   
  * ``association.route-table-id`` - The ID of the route table involved in the association. 
   
  * ``association.subnet-id`` - The ID of the subnet involved in the association. 
   
  * ``association.main`` - Indicates whether the route table is the main route table for the VPC (``true`` | ``false`` ). 
   
  * ``route-table-id`` - The ID of the route table. 
   
  * ``route.destination-cidr-block`` - The CIDR range specified in a route in the table. 
   
  * ``route.destination-prefix-list-id`` - The ID (prefix) of the AWS service specified in a route in the table. 
   
  * ``route.gateway-id`` - The ID of a gateway specified in a route in the table. 
   
  * ``route.instance-id`` - The ID of an instance specified in a route in the table. 
   
  * ``route.nat-gateway-id`` - The ID of a NAT gateway. 
   
  * ``route.origin`` - Describes how the route was created. ``create-route-table`` indicates that the route was automatically created when the route table was created; ``create-route`` indicates that the route was manually added to the route table; ``enable-vgw-route-propagation`` indicates that the route was propagated by route propagation. 
   
  * ``route.state`` - The state of a route in the route table (``active`` | ``blackhole`` ). The blackhole state indicates that the route's target isn't available (for example, the specified gateway isn't attached to the VPC, the specified NAT instance has been terminated, and so on). 
   
  * ``route.vpc-peering-connection-id`` - The ID of a VPC peering connection specified in a route in the table. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``vpc-id`` - The ID of the VPC for the route table. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your route tables**

This example describes your route tables.

Command::

  aws ec2 describe-route-tables

Output::

  {
      "RouteTables": [
          {
              "Associations": [
                  {
                      "RouteTableAssociationId": "rtbassoc-d8ccddba",
                      "Main": true,
                      "RouteTableId": "rtb-1f382e7d"
                  }
              ],
              "RouteTableId": "rtb-1f382e7d",
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
          },
          {
              "Associations": [
                  {
                      "SubnetId": "subnet-b61f49f0",
                      "RouteTableAssociationId": "rtbassoc-781d0d1a",
                      "RouteTableId": "rtb-22574640"
                  }
              ],
              "RouteTableId": "rtb-22574640",
              "VpcId": "vpc-a01106c2",
              "PropagatingVgws": [
                  {
                      "GatewayId": "vgw-f211f09b"
                  }
              ],
              "Tags": [],
              "Routes": [
                  {
                      "GatewayId": "local",
                      "DestinationCidrBlock": "10.0.0.0/16",
                      "State": "active"
                  },
                  {
                      "GatewayId": "igw-046d7966",
                      "DestinationCidrBlock": "0.0.0.0/0",
                      "State": "active"
                  }
              ]
          }          
      ]
  }

======
Output
======

RouteTables -> (list)

  

  Information about one or more route tables. 

  

  (structure)

    

    Describes a route table.

    

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
