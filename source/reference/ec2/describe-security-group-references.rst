[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-security-group-references:


**********************************
describe-security-group-references
**********************************



===========
Description
===========



[EC2-VPC only] Describes the VPCs on the other side of a VPC peering connection that are referencing the security groups you've specified in this request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeSecurityGroupReferences>`_


========
Synopsis
========

::

    describe-security-group-references
  [--dry-run | --no-dry-run]
  --group-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the operation, without actually making the request, and provides an error response. If you have the required permissions, the error response is DryRunOperation. Otherwise, it is UnauthorizedOperation.

  

``--group-id`` (list)


  One or more security group IDs in your account.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe security group references**

This example describes the security group references for ``sg-bbbb2222``. The response indicates that security group ``sg-bbbb2222`` is being referenced by a security group in VPC ``vpc-aaaaaaaa``.

Command::

  aws ec2 describe-security-group-references --group-id sg-bbbbb22222

Output::

  {    
    "SecurityGroupsReferenceSet": [
      {
        "ReferencingVpcId": "vpc-aaaaaaaa ",
        "GroupId": "sg-bbbbb22222", 
        "VpcPeeringConnectionId": "pcx-b04deed9"      
      }   
    ]
  }

======
Output
======

SecurityGroupReferenceSet -> (list)

  

  Information about the VPCs with the referencing security groups.

  

  (structure)

    

    Describes a VPC with a security group that references your security group.

    

    GroupId -> (string)

      

      The ID of your security group.

      

      

    ReferencingVpcId -> (string)

      

      The ID of the VPC with the referencing security group.

      

      

    VpcPeeringConnectionId -> (string)

      

      The ID of the VPC peering connection.

      

      

    

  

