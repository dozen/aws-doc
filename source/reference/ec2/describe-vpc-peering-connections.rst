[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpc-peering-connections:


********************************
describe-vpc-peering-connections
********************************



===========
Description
===========



Describes one or more of your VPC peering connections.



========
Synopsis
========

::

    describe-vpc-peering-connections
  [--dry-run | --no-dry-run]
  [--vpc-peering-connection-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-peering-connection-ids`` (list)


  One or more VPC peering connection IDs.

   

  Default: Describes all your VPC peering connections.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``accepter-vpc-info.cidr-block`` - The CIDR block of the peer VPC. 
   
  * ``accepter-vpc-info.owner-id`` - The AWS account ID of the owner of the peer VPC. 
   
  * ``accepter-vpc-info.vpc-id`` - The ID of the peer VPC. 
   
  * ``expiration-time`` - The expiration date and time for the VPC peering connection. 
   
  * ``requester-vpc-info.cidr-block`` - The CIDR block of the requesters VPC. 
   
  * ``requester-vpc-info.owner-id`` - The AWS account ID of the owner of the requester VPC. 
   
  * ``requester-vpc-info.vpc-id`` - The ID of the requester VPC. 
   
  * ``status-code`` - The status of the VPC peering connection (``pending-acceptance`` | ``failed`` | ``expired`` | ``provisioning`` | ``active`` | ``deleted`` | ``rejected`` ). 
   
  * ``status-message`` - A message that provides more information about the status of the VPC peering connection, if applicable. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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
                    "OwnerId": "444455556666",
                    "VpcId": "vpc-123abc45",
                    "CidrBlock": "10.0.0.0/28"
                }
            },
            {
                "Status": {
                    "Message": "Pending Acceptance by 123456789123",
                    "Code": "pending-acceptance"
                },
                "Tags": [
                    {
                        "Value": null,
                        "Key": "Name"
                    }
                ],
                "RequesterVpcInfo": {
                    "OwnerId": "123456789123",
                    "VpcId": "vpc-11aa22bb",
                    "CidrBlock": "10.0.0.0/28"
                },
                "VpcPeeringConnectionId": "pcx-abababab",
                "ExpirationTime": "2014-04-03T09:12:43.000Z",
                "AccepterVpcInfo": {
                    "OwnerId": "123456789123",
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

      

      

    

  

