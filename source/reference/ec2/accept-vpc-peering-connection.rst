[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 accept-vpc-peering-connection:


*****************************
accept-vpc-peering-connection
*****************************



===========
Description
===========



Accept a VPC peering connection request. To accept a request, the VPC peering connection must be in the ``pending-acceptance`` state, and you must be the owner of the peer VPC. Use the ``describe-vpc-peering-connections`` request to view your outstanding VPC peering connection requests.



========
Synopsis
========

::

    accept-vpc-peering-connection
  [--dry-run | --no-dry-run]
  [--vpc-peering-connection-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-peering-connection-id`` (string)


  The ID of the VPC peering connection.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    The information of the peer VPC.

    

    CidrBlock -> (string)

      

      The CIDR block for the VPC.

      

      

    OwnerId -> (string)

      

      The AWS account ID of the VPC owner.

      

      

    VpcId -> (string)

      

      The ID of the VPC.

      

      

    

  ExpirationTime -> (timestamp)

    

    The time that an unaccepted VPC peering connection will expire.

    

    

  RequesterVpcInfo -> (structure)

    

    The information of the requester VPC.

    

    CidrBlock -> (string)

      

      The CIDR block for the VPC.

      

      

    OwnerId -> (string)

      

      The AWS account ID of the VPC owner.

      

      

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

    

    

  

