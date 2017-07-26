[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 accept-vpc-peering-connection:


*****************************
accept-vpc-peering-connection
*****************************



===========
Description
===========



Accept a VPC peering connection request. To accept a request, the VPC peering connection must be in the ``pending-acceptance`` state, and you must be the owner of the peer VPC. Use  describe-vpc-peering-connections to view your outstanding VPC peering connection requests.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AcceptVpcPeeringConnection>`_


========
Synopsis
========

::

    accept-vpc-peering-connection
  [--dry-run | --no-dry-run]
  [--vpc-peering-connection-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-peering-connection-id`` (string)


  The ID of the VPC peering connection.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To accept a VPC peering connection**

This example accepts the specified VPC peering connection request.

Command::

  aws ec2 accept-vpc-peering-connection --vpc-peering-connection-id pcx-1a2b3c4d

Output::

  {
    "VpcPeeringConnection": {
      "Status": {
        "Message": "Provisioning",
        "Code": "provisioning"
      },
      "Tags": [],
      "AccepterVpcInfo": {
        "OwnerId": "444455556666",
        "VpcId": "vpc-44455566",
        "CidrBlock": "10.0.1.0/28"
      },
      "VpcPeeringConnectionId": "pcx-1a2b3c4d",
      "RequesterVpcInfo": {
        "OwnerId": "444455556666",
        "VpcId": "vpc-111abc45",
        "CidrBlock": "10.0.0.0/28"
      }
    }
  }

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

    

    

  

