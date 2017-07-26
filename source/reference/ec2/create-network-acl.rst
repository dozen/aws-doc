[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-network-acl:


******************
create-network-acl
******************



===========
Description
===========



Creates a network ACL in a VPC. Network ACLs provide an optional layer of security (in addition to security groups) for the instances in your VPC.

 

For more information about network ACLs, see `Network ACLs`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    create-network-acl
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

**To create a network ACL**

This example creates a network ACL for the specified VPC.

Command::

  aws ec2 create-network-acl --vpc-id vpc-a01106c2

Output::

  {
      "NetworkAcl": {
          "Associations": [],
          "NetworkAclId": "acl-5fb85d36",
          "VpcId": "vpc-a01106c2",
          "Tags": [],
          "Entries": [
              {
                  "CidrBlock": "0.0.0.0/0",
                  "RuleNumber": 32767,
                  "Protocol": "-1",
                  "Egress": true,
                  "RuleAction": "deny"
              },
              {
                  "CidrBlock": "0.0.0.0/0",
                  "RuleNumber": 32767,
                  "Protocol": "-1",
                  "Egress": false,
                  "RuleAction": "deny"
              }
          ],
          "IsDefault": false
      }  
  }

======
Output
======

NetworkAcl -> (structure)

  

  Information about the network ACL.

  

  NetworkAclId -> (string)

    

    The ID of the network ACL.

    

    

  VpcId -> (string)

    

    The ID of the VPC for the network ACL.

    

    

  IsDefault -> (boolean)

    

    Indicates whether this is the default network ACL for the VPC.

    

    

  Entries -> (list)

    

    One or more entries (rules) in the network ACL.

    

    (structure)

      

      Describes an entry in a network ACL.

      

      RuleNumber -> (integer)

        

        The rule number for the entry. ACL entries are processed in ascending order by rule number.

        

        

      Protocol -> (string)

        

        The protocol. A value of ``-1`` means all protocols.

        

        

      RuleAction -> (string)

        

        Indicates whether to allow or deny the traffic that matches the rule.

        

        

      Egress -> (boolean)

        

        Indicates whether the rule is an egress rule (applied to traffic leaving the subnet).

        

        

      CidrBlock -> (string)

        

        The network range to allow or deny, in CIDR notation.

        

        

      IcmpTypeCode -> (structure)

        

        ICMP protocol: The ICMP type and code.

        

        Type -> (integer)

          

          The ICMP code. A value of -1 means all codes for the specified ICMP type.

          

          

        Code -> (integer)

          

          The ICMP type. A value of -1 means all types.

          

          

        

      PortRange -> (structure)

        

        TCP or UDP protocols: The range of ports the rule applies to.

        

        From -> (integer)

          

          The first port in the range.

          

          

        To -> (integer)

          

          The last port in the range.

          

          

        

      

    

  Associations -> (list)

    

    Any associations between the network ACL and one or more subnets

    

    (structure)

      

      Describes an association between a network ACL and a subnet.

      

      NetworkAclAssociationId -> (string)

        

        The ID of the association between a network ACL and a subnet.

        

        

      NetworkAclId -> (string)

        

        The ID of the network ACL.

        

        

      SubnetId -> (string)

        

        The ID of the subnet.

        

        

      

    

  Tags -> (list)

    

    Any tags assigned to the network ACL.

    

    (structure)

      

      Describes a tag.

      

      Key -> (string)

        

        The key of the tag. 

         

        Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

        

        

      Value -> (string)

        

        The value of the tag.

         

        Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

        

        

      

    

  



.. _Network ACLs: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html
