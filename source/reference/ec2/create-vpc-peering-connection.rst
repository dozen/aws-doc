[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-vpc-peering-connection:


*****************************
create-vpc-peering-connection
*****************************



===========
Description
===========



Requests a VPC peering connection between two VPCs: a requester VPC that you own and a peer VPC with which to create the connection. The peer VPC can belong to another AWS account. The requester VPC and peer VPC cannot have overlapping CIDR blocks.

 

The owner of the peer VPC must accept the peering request to activate the peering connection. The VPC peering connection request expires after 7 days, after which it cannot be accepted or rejected.

 

If you try to create a VPC peering connection between VPCs that have overlapping CIDR blocks, the VPC peering connection status goes to ``failed`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateVpcPeeringConnection>`_


========
Synopsis
========

::

    create-vpc-peering-connection
  [--dry-run | --no-dry-run]
  [--peer-owner-id <value>]
  [--peer-vpc-id <value>]
  [--vpc-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--peer-owner-id`` (string)


  The AWS account ID of the owner of the peer VPC.

   

  Default: Your AWS account ID

  

``--peer-vpc-id`` (string)


  The ID of the VPC with which you are creating the VPC peering connection.

  

``--vpc-id`` (string)


  The ID of the requester VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a VPC peering connection between your VPCs**

This example requests a peering connection between your VPCs vpc-1a2b3c4d and vpc-11122233.

Command::

  aws ec2 create-vpc-peering-connection --vpc-id vpc-1a2b3c4d --peer-vpc-id vpc-11122233

Output::

    {
        "VpcPeeringConnection": {
            "Status": {
                "Message": "Initiating Request to 444455556666",
                "Code": "initiating-request"
            },
            "Tags": [],
            "RequesterVpcInfo": {
                "OwnerId": "444455556666",
                "VpcId": "vpc-1a2b3c4d",
                "CidrBlock": "10.0.0.0/28"
            },
            "VpcPeeringConnectionId": "pcx-111aaa111",
            "ExpirationTime": "2014-04-02T16:13:36.000Z",
            "AccepterVpcInfo": {
                "OwnerId": "444455556666",
                "VpcId": "vpc-11122233"
            }
        }
    }

**To create a VPC peering connection with a VPC in another account**

This example requests a peering connection between your VPC (vpc-1a2b3c4d), and a VPC (vpc-123abc45) that belongs AWS account 123456789012.

Command::

  aws ec2 create-vpc-peering-connection --vpc-id vpc-1a2b3c4d --peer-vpc-id vpc-11122233 --peer-owner-id 123456789012



======
Output
======

VpcPeeringConnection -> (structure)

  

  Information about the VPC peering connection.

  

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

    

    

  

