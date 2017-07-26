[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpc-peering-connections:


********************************
describe-vpc-peering-connections
********************************



===========
Description
===========



Describes one or more of your VPC peering connections.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeVpcPeeringConnections>`_


========
Synopsis
========

::

    describe-vpc-peering-connections
  [--filters <value>]
  [--dry-run | --no-dry-run]
  [--vpc-peering-connection-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``accepter-vpc-info.cidr-block`` - The IPv4 CIDR block of the peer VPC. 
   
  * ``accepter-vpc-info.owner-id`` - The AWS account ID of the owner of the peer VPC. 
   
  * ``accepter-vpc-info.vpc-id`` - The ID of the peer VPC. 
   
  * ``expiration-time`` - The expiration date and time for the VPC peering connection. 
   
  * ``requester-vpc-info.cidr-block`` - The IPv4 CIDR block of the requester's VPC. 
   
  * ``requester-vpc-info.owner-id`` - The AWS account ID of the owner of the requester VPC. 
   
  * ``requester-vpc-info.vpc-id`` - The ID of the requester VPC. 
   
  * ``status-code`` - The status of the VPC peering connection (``pending-acceptance`` | ``failed`` | ``expired`` | ``provisioning`` | ``active`` | ``deleted`` | ``rejected`` ). 
   
  * ``status-message`` - A message that provides more information about the status of the VPC peering connection, if applicable. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``vpc-peering-connection-id`` - The ID of the VPC peering connection. 
   

  



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



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-peering-connection-ids`` (list)


  One or more VPC peering connection IDs.

   

  Default: Describes all your VPC peering connections.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your VPC peering connections**

This example describes all of your VPC peering connections.

Command::

  aws ec2 describe-vpc-peering-connections

Output::

    {
        "VpcPeeringConnections": [
            {
                "Status": {
                    "Message": "Active",
                    "Code": "active"
                },
                "Tags": [
                    {
                        "Value": "Peering-1",
                        "Key": "Name"
                    }
                ],
                "AccepterVpcInfo": {
                    "OwnerId": "111122223333",
                    "VpcId": "vpc-1a2b3c4d",
                    "CidrBlock": "10.0.1.0/28"
                },
                "VpcPeeringConnectionId": "pcx-11122233",
                "RequesterVpcInfo": {
                    "PeeringOptions": {
                        "AllowEgressFromLocalVpcToRemoteClassicLink": false, 
                        "AllowEgressFromLocalClassicLinkToRemoteVpc": false
                    },
                    "OwnerId": "444455556666",
                    "VpcId": "vpc-123abc45",
                    "CidrBlock": "192.168.0.0/16"
                }
            },
            {
                "Status": {
                    "Message": "Pending Acceptance by 444455556666",
                    "Code": "pending-acceptance"
                },
                "Tags": [],
                "RequesterVpcInfo": {
                    "PeeringOptions": {
                        "AllowEgressFromLocalVpcToRemoteClassicLink": false, 
                        "AllowEgressFromLocalClassicLinkToRemoteVpc": false
                    },
                    "OwnerId": "444455556666",
                    "VpcId": "vpc-11aa22bb",
                    "CidrBlock": "10.0.0.0/28"
                },
                "VpcPeeringConnectionId": "pcx-abababab",
                "ExpirationTime": "2014-04-03T09:12:43.000Z",
                "AccepterVpcInfo": {
                    "OwnerId": "444455556666",
                    "VpcId": "vpc-33cc44dd"
                }
            }
        ]
    }


**To describe specific VPC peering connections**

This example describes all of your VPC peering connections that are in the pending-acceptance state.

Command::

  aws ec2 describe-vpc-peering-connections --filters Name=status-code,Values=pending-acceptance


This example describes all of your VPC peering connections that have the tag Name=Finance or Name=Accounts.

Command::

  aws ec2 describe-vpc-peering-connections --filters Name=tag-key,Values=Name Name=tag-value,Values=Finance,Accounts


This example describes all of the VPC peering connections you requested for the specified VPC, vpc-1a2b3c4d.

Command::

  aws ec2 describe-vpc-peering-connections --filters Name=requester-vpc-info.vpc-id,Values=vpc-1a2b3c4d



======
Output
======

VpcPeeringConnections -> (list)

  

  Information about the VPC peering connections.

  

  (structure)

    

    Describes a VPC peering connection.

    

    AccepterVpcInfo -> (structure)

      

      Information about the accepter VPC. CIDR block information is only returned when describing an active VPC peering connection.

      

      CidrBlock -> (string)

        

        The IPv4 CIDR block for the VPC.

        

        

      Ipv6CidrBlockSet -> (list)

        

        The IPv6 CIDR block for the VPC.

        

        (structure)

          

          Describes an IPv6 CIDR block.

          

          Ipv6CidrBlock -> (string)

            

            The IPv6 CIDR block.

            

            

          

        

      OwnerId -> (string)

        

        The AWS account ID of the VPC owner.

        

        

      PeeringOptions -> (structure)

        

        Information about the VPC peering connection options for the accepter or requester VPC.

        

        AllowDnsResolutionFromRemoteVpc -> (boolean)

          

          Indicates whether a local VPC can resolve public DNS hostnames to private IP addresses when queried from instances in a peer VPC.

          

          

        AllowEgressFromLocalClassicLinkToRemoteVpc -> (boolean)

          

          Indicates whether a local ClassicLink connection can communicate with the peer VPC over the VPC peering connection.

          

          

        AllowEgressFromLocalVpcToRemoteClassicLink -> (boolean)

          

          Indicates whether a local VPC can communicate with a ClassicLink connection in the peer VPC over the VPC peering connection.

          

          

        

      VpcId -> (string)

        

        The ID of the VPC.

        

        

      

    ExpirationTime -> (timestamp)

      

      The time that an unaccepted VPC peering connection will expire.

      

      

    RequesterVpcInfo -> (structure)

      

      Information about the requester VPC. CIDR block information is only returned when describing an active VPC peering connection.

      

      CidrBlock -> (string)

        

        The IPv4 CIDR block for the VPC.

        

        

      Ipv6CidrBlockSet -> (list)

        

        The IPv6 CIDR block for the VPC.

        

        (structure)

          

          Describes an IPv6 CIDR block.

          

          Ipv6CidrBlock -> (string)

            

            The IPv6 CIDR block.

            

            

          

        

      OwnerId -> (string)

        

        The AWS account ID of the VPC owner.

        

        

      PeeringOptions -> (structure)

        

        Information about the VPC peering connection options for the accepter or requester VPC.

        

        AllowDnsResolutionFromRemoteVpc -> (boolean)

          

          Indicates whether a local VPC can resolve public DNS hostnames to private IP addresses when queried from instances in a peer VPC.

          

          

        AllowEgressFromLocalClassicLinkToRemoteVpc -> (boolean)

          

          Indicates whether a local ClassicLink connection can communicate with the peer VPC over the VPC peering connection.

          

          

        AllowEgressFromLocalVpcToRemoteClassicLink -> (boolean)

          

          Indicates whether a local VPC can communicate with a ClassicLink connection in the peer VPC over the VPC peering connection.

          

          

        

      VpcId -> (string)

        

        The ID of the VPC.

        

        

      

    Status -> (structure)

      

      The status of the VPC peering connection.

      

      Code -> (string)

        

        The status of the VPC peering connection.

        

        

      Message -> (string)

        

        A message that provides more information about the status, if applicable.

        

        

      

    Tags -> (list)

      

      Any tags assigned to the resource.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag.

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    VpcPeeringConnectionId -> (string)

      

      The ID of the VPC peering connection.

      

      

    

  

