[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-network-acls:


*********************
describe-network-acls
*********************



===========
Description
===========



Describes one or more of your network ACLs.

 

For more information about network ACLs, see `Network ACLs`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    describe-network-acls
  [--dry-run | --no-dry-run]
  [--network-acl-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--network-acl-ids`` (list)


  One or more network ACL IDs.

   

  Default: Describes all your network ACLs.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``association.association-id`` - The ID of an association ID for the ACL. 
   
  * ``association.network-acl-id`` - The ID of the network ACL involved in the association. 
   
  * ``association.subnet-id`` - The ID of the subnet involved in the association. 
   
  * ``default`` - Indicates whether the ACL is the default network ACL for the VPC. 
   
  * ``entry.cidr`` - The CIDR range specified in the entry. 
   
  * ``entry.egress`` - Indicates whether the entry applies to egress traffic. 
   
  * ``entry.icmp.code`` - The ICMP code specified in the entry, if any. 
   
  * ``entry.icmp.type`` - The ICMP type specified in the entry, if any. 
   
  * ``entry.port-range.from`` - The start of the port range specified in the entry.  
   
  * ``entry.port-range.to`` - The end of the port range specified in the entry.  
   
  * ``entry.protocol`` - The protocol specified in the entry (``tcp`` | ``udp`` | ``icmp`` or a protocol number). 
   
  * ``entry.rule-action`` - Allows or denies the matching traffic (``allow`` | ``deny`` ). 
   
  * ``entry.rule-number`` - The number of an entry (in other words, rule) in the ACL's set of entries. 
   
  * ``network-acl-id`` - The ID of the network ACL. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``vpc-id`` - The ID of the VPC for the network ACL. 
   

  



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

**To describe your network ACLs**

This example describes your network ACLs.

Command::

  aws ec2 describe-network-acls

Output::

  {
      "NetworkAcls": [
          {
              "Associations": [],
              "NetworkAclId": "acl-7aaabd18",
              "VpcId": "vpc-a01106c2",
              "Tags": [],
              "Entries": [
                  {
                      "CidrBlock": "0.0.0.0/0",
                      "RuleNumber": 100,
                      "Protocol": "-1",
                      "Egress": true,
                      "RuleAction": "allow"
                  },
                  {
                      "CidrBlock": "0.0.0.0/0",
                      "RuleNumber": 32767,
                      "Protocol": "-1",
                      "Egress": true,
                      "RuleAction": "deny"
                  },
                  {
                      "CidrBlock": "0.0.0.0/0",
                      "RuleNumber": 100,
                      "Protocol": "-1",
                      "Egress": false,
                      "RuleAction": "allow"
                  },
                  {
                      "CidrBlock": "0.0.0.0/0",
                      "RuleNumber": 32767,
                      "Protocol": "-1",
                      "Egress": false,
                      "RuleAction": "deny"
                  }
              ],
              "IsDefault": true
          },  
          {
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
          },
          {
              "Associations": [
                  {
                      "SubnetId": "subnet-6bea5f06",
                      "NetworkAclId": "acl-9aeb5ef7",
                      "NetworkAclAssociationId": "aclassoc-67ea5f0a"
                  },
                  {
                      "SubnetId": "subnet-65ea5f08",
                      "NetworkAclId": "acl-9aeb5ef7",
                      "NetworkAclAssociationId": "aclassoc-66ea5f0b"
                  }
              ],
              "NetworkAclId": "acl-9aeb5ef7",
              "VpcId": "vpc-98eb5ef5",
              "Tags": [],
              "Entries": [
                  {
                      "CidrBlock": "0.0.0.0/0",
                      "RuleNumber": 100,
                      "Protocol": "-1",
                      "Egress": true,
                      "RuleAction": "allow"
                  },
                  {
                      "CidrBlock": "0.0.0.0/0",
                      "RuleNumber": 32767,
                      "Protocol": "-1",
                      "Egress": true,
                      "RuleAction": "deny"
                  },
                  {
                      "CidrBlock": "0.0.0.0/0",
                      "RuleNumber": 100,
                      "Protocol": "-1",
                      "Egress": false,
                      "RuleAction": "allow"
                  },
                  {
                      "CidrBlock": "0.0.0.0/0",
                      "RuleNumber": 32767,
                      "Protocol": "-1",
                      "Egress": false,
                      "RuleAction": "deny"
                  }
              ],
              "IsDefault": true
          }          
      ]
  }

======
Output
======

NetworkAcls -> (list)

  

  Information about one or more network ACLs.

  

  (structure)

    

    Describes a network ACL.

    

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
