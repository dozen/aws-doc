[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-security-groups:


************************
describe-security-groups
************************



===========
Description
===========



Describes one or more of your security groups.

 

A security group is for use with instances either in the EC2-Classic platform or in a specific VPC. For more information, see `Amazon EC2 Security Groups <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html>`_ in the *Amazon Elastic Compute Cloud User Guide* and `Security Groups for Your VPC <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_SecurityGroups.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeSecurityGroups>`_


========
Synopsis
========

::

    describe-security-groups
  [--filters <value>]
  [--group-ids <value>]
  [--group-names <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters. If using multiple filters for rules, the results include security groups for which any combination of rules - not necessarily a single rule - match all filters.

   

   
  * ``description`` - The description of the security group. 
   
  * ``egress.ip-permission.prefix-list-id`` - The ID (prefix) of the AWS service to which the security group allows access. 
   
  * ``group-id`` - The ID of the security group.  
   
  * ``group-name`` - The name of the security group. 
   
  * ``ip-permission.cidr`` - An IPv4 CIDR range that has been granted permission in a security group rule. 
   
  * ``ip-permission.from-port`` - The start of port range for the TCP and UDP protocols, or an ICMP type number. 
   
  * ``ip-permission.group-id`` - The ID of a security group that has been granted permission. 
   
  * ``ip-permission.group-name`` - The name of a security group that has been granted permission. 
   
  * ``ip-permission.ipv6-cidr`` - An IPv6 CIDR range that has been granted permission in a security group rule. 
   
  * ``ip-permission.protocol`` - The IP protocol for the permission (``tcp`` | ``udp`` | ``icmp`` or a protocol number). 
   
  * ``ip-permission.to-port`` - The end of port range for the TCP and UDP protocols, or an ICMP code. 
   
  * ``ip-permission.user-id`` - The ID of an AWS account that has been granted permission. 
   
  * ``owner-id`` - The AWS account ID of the owner of the security group. 
   
  * ``tag-key`` - The key of a tag assigned to the security group. 
   
  * ``tag-value`` - The value of a tag assigned to the security group. 
   
  * ``vpc-id`` - The ID of the VPC specified when the security group was created. 
   

  



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



``--group-ids`` (list)


  One or more security group IDs. Required for security groups in a nondefault VPC.

   

  Default: Describes all your security groups.

  



Syntax::

  "string" "string" ...



``--group-names`` (list)


  [EC2-Classic and default VPC only] One or more security group names. You can specify either the security group name or the security group ID. For security groups in a nondefault VPC, use the ``group-name`` filter to describe security groups by name.

   

  Default: Describes all your security groups.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a security group for EC2-Classic**

This example displays information about the security group named ``MySecurityGroup``.

Command::

  aws ec2 describe-security-groups --group-names MySecurityGroup

Output::

  {
      "SecurityGroups": [
          {
              "IpPermissionsEgress": [],
              "Description": "My security group",
              "IpPermissions": [
                  {
                      "PrefixListIds": [], 
                      "FromPort": 22, 
                      "IpRanges": [
                          {
                              "CidrIp": "203.0.113.0/24"
                          }
                      ], 
                      "ToPort": 22, 
                      "IpProtocol": "tcp", 
                      "UserIdGroupPairs": []
                  }
              ],
              "GroupName": "MySecurityGroup",
              "OwnerId": "123456789012",
              "GroupId": "sg-903004f8",
          }
      ]
  }

**To describe a security group for EC2-VPC**

This example displays information about the security group with the ID sg-903004f8. Note that you can't reference a security group for EC2-VPC by name.

Command::

  aws ec2 describe-security-groups --group-ids sg-903004f8

Output::

  {
      "SecurityGroups": [
          {
              "IpPermissionsEgress": [
                  {
                      "IpProtocol": "-1",
                      "IpRanges": [
                          {
                              "CidrIp": "0.0.0.0/0"
                          }
                      ],
                      "UserIdGroupPairs": [],
                      "PrefixListIds": []
                  }
              ],
              "Description": "My security group",
              "Tags": [
                  {
                      "Value": "SG1", 
                      "Key": "Name"
                   }
              ], 
              "IpPermissions": [
                  {
                      "IpProtocol": "-1", 
                      "IpRanges": [], 
                      "UserIdGroupPairs": [
                          {
                               "UserId": "123456789012", 
                               "GroupId": "sg-903004f8"
                          }
                      ], 
                      "PrefixListIds": []
                  },
                  {
                      "PrefixListIds": [], 
                      "FromPort": 22, 
                      "IpRanges": [
                          {
                              "CidrIp": "203.0.113.0/24"
                          }
                      ], 
                      "ToPort": 22, 
                      "IpProtocol": "tcp", 
                      "UserIdGroupPairs": []
                    }
              ],
              "GroupName": "MySecurityGroup",
              "VpcId": "vpc-1a2b3c4d",
              "OwnerId": "123456789012",
              "GroupId": "sg-903004f8",
          }
      ]
  }

**To describe security groups that have specific rules**

(EC2-VPC only) This example uses filters to describe security groups that have a rule that allows SSH traffic (port 22) and a rule that allows traffic from all addresses (``0.0.0.0/0``). The output is filtered to display only the names of the security groups. Security groups must match all filters to be returned in the results; however, a single rule does not have to match all filters. For example, the output returns a security group with a rule that allows SSH traffic from a specific IP address and another rule that allows HTTP traffic from all addresses.

Command::

  aws ec2 describe-security-groups --filters Name=ip-permission.from-port,Values=22 Name=ip-permission.to-port,Values=22 Name=ip-permission.cidr,Values='0.0.0.0/0' --query 'SecurityGroups[*].{Name:GroupName}'

Output::

   [
     {
        "Name": "default"
     }, 
     {
        "Name": "Test SG"
     }, 
     {
        "Name": "SSH-Access-Group"
     }
   ]

**To describe tagged security groups**

This example describes all security groups that include ``test`` in the security group name, and that have the tag ``Test=To-delete``. The output is filtered to display only the names and IDs of the security groups.

Command::

  aws ec2 describe-security-groups --filters Name=group-name,Values='*test*' Name=tag-key,Values=Test Name=tag-value,Values=To-delete --query 'SecurityGroups[*].{Name:GroupName,ID:GroupId}'
  
Output::

   [
     {
        "Name": "testfornewinstance", 
        "ID": "sg-33bb22aa"
     }, 
     {
        "Name": "newgrouptest", 
        "ID": "sg-1a2b3c4d"
     }
   ]

For more information, see `Using Security Groups`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Security Groups`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-sg.html



======
Output
======

SecurityGroups -> (list)

  

  Information about one or more security groups.

  

  (structure)

    

    Describes a security group

    

    Description -> (string)

      

      A description of the security group.

      

      

    GroupName -> (string)

      

      The name of the security group.

      

      

    IpPermissions -> (list)

      

      One or more inbound rules associated with the security group.

      

      (structure)

        

        Describes a security group rule.

        

        FromPort -> (integer)

          

          The start of port range for the TCP and UDP protocols, or an ICMP/ICMPv6 type number. A value of ``-1`` indicates all ICMP/ICMPv6 types.

          

          

        IpProtocol -> (string)

          

          The IP protocol name (``tcp`` , ``udp`` , ``icmp`` ) or number (see `Protocol Numbers <http://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml>`_ ). 

           

          [EC2-VPC only] Use ``-1`` to specify all protocols. When authorizing security group rules, specifying ``-1`` or a protocol number other than ``tcp`` , ``udp`` , ``icmp`` , or ``58`` (ICMPv6) allows traffic on all ports, regardless of any port range you specify. For ``tcp`` , ``udp`` , and ``icmp`` , you must specify a port range. For ``58`` (ICMPv6), you can optionally specify a port range; if you don't, traffic for all types and codes is allowed when authorizing rules. 

          

          

        IpRanges -> (list)

          

          One or more IPv4 ranges.

          

          (structure)

            

            Describes an IPv4 range.

            

            CidrIp -> (string)

              

              The IPv4 CIDR range. You can either specify a CIDR range or a source security group, not both. To specify a single IPv4 address, use the /32 prefix.

              

              

            

          

        Ipv6Ranges -> (list)

          

          [EC2-VPC only] One or more IPv6 ranges.

          

          (structure)

            

            [EC2-VPC only] Describes an IPv6 range.

            

            CidrIpv6 -> (string)

              

              The IPv6 CIDR range. You can either specify a CIDR range or a source security group, not both. To specify a single IPv6 address, use the /128 prefix.

              

              

            

          

        PrefixListIds -> (list)

          

          (Valid for  authorize-security-group-egress ,  revoke-security-group-egress and  describe-security-groups only) One or more prefix list IDs for an AWS service. In an  authorize-security-group-egress request, this is the AWS service that you want to access through a VPC endpoint from instances associated with the security group.

          

          (structure)

            

            The ID of the prefix.

            

            PrefixListId -> (string)

              

              The ID of the prefix.

              

              

            

          

        ToPort -> (integer)

          

          The end of port range for the TCP and UDP protocols, or an ICMP/ICMPv6 code. A value of ``-1`` indicates all ICMP/ICMPv6 codes for the specified ICMP type.

          

          

        UserIdGroupPairs -> (list)

          

          One or more security group and AWS account ID pairs.

          

          (structure)

            

            Describes a security group and AWS account ID pair.

            

            GroupId -> (string)

              

              The ID of the security group.

              

              

            GroupName -> (string)

              

              The name of the security group. In a request, use this parameter for a security group in EC2-Classic or a default VPC only. For a security group in a nondefault VPC, use the security group ID.

              

              

            PeeringStatus -> (string)

              

              The status of a VPC peering connection, if applicable.

              

              

            UserId -> (string)

              

              The ID of an AWS account. For a referenced security group in another VPC, the account ID of the referenced security group is returned.

               

              [EC2-Classic] Required when adding or removing rules that reference a security group in another AWS account.

              

              

            VpcId -> (string)

              

              The ID of the VPC for the referenced security group, if applicable.

              

              

            VpcPeeringConnectionId -> (string)

              

              The ID of the VPC peering connection, if applicable.

              

              

            

          

        

      

    OwnerId -> (string)

      

      The AWS account ID of the owner of the security group.

      

      

    GroupId -> (string)

      

      The ID of the security group.

      

      

    IpPermissionsEgress -> (list)

      

      [EC2-VPC] One or more outbound rules associated with the security group.

      

      (structure)

        

        Describes a security group rule.

        

        FromPort -> (integer)

          

          The start of port range for the TCP and UDP protocols, or an ICMP/ICMPv6 type number. A value of ``-1`` indicates all ICMP/ICMPv6 types.

          

          

        IpProtocol -> (string)

          

          The IP protocol name (``tcp`` , ``udp`` , ``icmp`` ) or number (see `Protocol Numbers <http://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml>`_ ). 

           

          [EC2-VPC only] Use ``-1`` to specify all protocols. When authorizing security group rules, specifying ``-1`` or a protocol number other than ``tcp`` , ``udp`` , ``icmp`` , or ``58`` (ICMPv6) allows traffic on all ports, regardless of any port range you specify. For ``tcp`` , ``udp`` , and ``icmp`` , you must specify a port range. For ``58`` (ICMPv6), you can optionally specify a port range; if you don't, traffic for all types and codes is allowed when authorizing rules. 

          

          

        IpRanges -> (list)

          

          One or more IPv4 ranges.

          

          (structure)

            

            Describes an IPv4 range.

            

            CidrIp -> (string)

              

              The IPv4 CIDR range. You can either specify a CIDR range or a source security group, not both. To specify a single IPv4 address, use the /32 prefix.

              

              

            

          

        Ipv6Ranges -> (list)

          

          [EC2-VPC only] One or more IPv6 ranges.

          

          (structure)

            

            [EC2-VPC only] Describes an IPv6 range.

            

            CidrIpv6 -> (string)

              

              The IPv6 CIDR range. You can either specify a CIDR range or a source security group, not both. To specify a single IPv6 address, use the /128 prefix.

              

              

            

          

        PrefixListIds -> (list)

          

          (Valid for  authorize-security-group-egress ,  revoke-security-group-egress and  describe-security-groups only) One or more prefix list IDs for an AWS service. In an  authorize-security-group-egress request, this is the AWS service that you want to access through a VPC endpoint from instances associated with the security group.

          

          (structure)

            

            The ID of the prefix.

            

            PrefixListId -> (string)

              

              The ID of the prefix.

              

              

            

          

        ToPort -> (integer)

          

          The end of port range for the TCP and UDP protocols, or an ICMP/ICMPv6 code. A value of ``-1`` indicates all ICMP/ICMPv6 codes for the specified ICMP type.

          

          

        UserIdGroupPairs -> (list)

          

          One or more security group and AWS account ID pairs.

          

          (structure)

            

            Describes a security group and AWS account ID pair.

            

            GroupId -> (string)

              

              The ID of the security group.

              

              

            GroupName -> (string)

              

              The name of the security group. In a request, use this parameter for a security group in EC2-Classic or a default VPC only. For a security group in a nondefault VPC, use the security group ID.

              

              

            PeeringStatus -> (string)

              

              The status of a VPC peering connection, if applicable.

              

              

            UserId -> (string)

              

              The ID of an AWS account. For a referenced security group in another VPC, the account ID of the referenced security group is returned.

               

              [EC2-Classic] Required when adding or removing rules that reference a security group in another AWS account.

              

              

            VpcId -> (string)

              

              The ID of the VPC for the referenced security group, if applicable.

              

              

            VpcPeeringConnectionId -> (string)

              

              The ID of the VPC peering connection, if applicable.

              

              

            

          

        

      

    Tags -> (list)

      

      Any tags assigned to the security group.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag.

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    VpcId -> (string)

      

      [EC2-VPC] The ID of the VPC for the security group.

      

      

    

  

