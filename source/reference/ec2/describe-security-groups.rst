[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-security-groups:


************************
describe-security-groups
************************



===========
Description
===========



Describes one or more of your security groups.

 

A security group is for use with instances either in the EC2-Classic platform or in a specific VPC. For more information, see `Amazon EC2 Security Groups`_ in the *Amazon Elastic Compute Cloud User Guide* and `Security Groups for Your VPC`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    describe-security-groups
  [--dry-run | --no-dry-run]
  [--group-names <value>]
  [--group-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--group-names`` (list)


  [EC2-Classic and default VPC only] One or more security group names. You can specify either the security group name or the security group ID. For security groups in a nondefault VPC, use the ``group-name`` filter to describe security groups by name.

   

  Default: Describes all your security groups.

  



Syntax::

  "string" "string" ...



``--group-ids`` (list)


  One or more security group IDs. Required for security groups in a nondefault VPC.

   

  Default: Describes all your security groups.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters. If using multiple filters for rules, the results include security groups for which any combination of rules - not necessarily a single rule - match all filters.

   

   
  * ``description`` - The description of the security group. 
   
  * ``egress.ip-permission.prefix-list-id`` - The ID (prefix) of the AWS service to which the security group allows access. 
   
  * ``group-id`` - The ID of the security group.  
   
  * ``group-name`` - The name of the security group. 
   
  * ``ip-permission.cidr`` - A CIDR range that has been granted permission. 
   
  * ``ip-permission.from-port`` - The start of port range for the TCP and UDP protocols, or an ICMP type number. 
   
  * ``ip-permission.group-id`` - The ID of a security group that has been granted permission. 
   
  * ``ip-permission.group-name`` - The name of a security group that has been granted permission. 
   
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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    OwnerId -> (string)

      

      The AWS account ID of the owner of the security group.

      

      

    GroupName -> (string)

      

      The name of the security group.

      

      

    GroupId -> (string)

      

      The ID of the security group.

      

      

    Description -> (string)

      

      A description of the security group.

      

      

    IpPermissions -> (list)

      

      One or more inbound rules associated with the security group.

      

      (structure)

        

        Describes a security group rule.

        

        IpProtocol -> (string)

          

          The IP protocol name (for ``tcp`` , ``udp`` , and ``icmp`` ) or number (see `Protocol Numbers`_ ). 

           

          [EC2-VPC only] When you authorize or revoke security group rules, you can use ``-1`` to specify all.

          

          

        FromPort -> (integer)

          

          The start of port range for the TCP and UDP protocols, or an ICMP type number. A value of ``-1`` indicates all ICMP types.

          

          

        ToPort -> (integer)

          

          The end of port range for the TCP and UDP protocols, or an ICMP code. A value of ``-1`` indicates all ICMP codes for the specified ICMP type.

          

          

        UserIdGroupPairs -> (list)

          

          One or more security group and AWS account ID pairs.

          

          (structure)

            

            Describes a security group and AWS account ID pair. 

            

            UserId -> (string)

              

              The ID of an AWS account. EC2-Classic only.

              

              

            GroupName -> (string)

              

              The name of the security group. In a request, use this parameter for a security group in EC2-Classic or a default VPC only. For a security group in a nondefault VPC, use ``GroupId`` .

              

              

            GroupId -> (string)

              

              The ID of the security group.

              

              

            

          

        IpRanges -> (list)

          

          One or more IP ranges.

          

          (structure)

            

            Describes an IP range.

            

            CidrIp -> (string)

              

              The CIDR range. You can either specify a CIDR range or a source security group, not both.

              

              

            

          

        PrefixListIds -> (list)

          

          (Valid for  authorize-security-group-egress ,  revoke-security-group-egress and  describe-security-groups only) One or more prefix list IDs for an AWS service. In an  authorize-security-group-egress request, this is the AWS service that you want to access through a VPC endpoint from instances associated with the security group.

          

          (structure)

            

            The ID of the prefix.

            

            PrefixListId -> (string)

              

              The ID of the prefix.

              

              

            

          

        

      

    IpPermissionsEgress -> (list)

      

      [EC2-VPC] One or more outbound rules associated with the security group.

      

      (structure)

        

        Describes a security group rule.

        

        IpProtocol -> (string)

          

          The IP protocol name (for ``tcp`` , ``udp`` , and ``icmp`` ) or number (see `Protocol Numbers`_ ). 

           

          [EC2-VPC only] When you authorize or revoke security group rules, you can use ``-1`` to specify all.

          

          

        FromPort -> (integer)

          

          The start of port range for the TCP and UDP protocols, or an ICMP type number. A value of ``-1`` indicates all ICMP types.

          

          

        ToPort -> (integer)

          

          The end of port range for the TCP and UDP protocols, or an ICMP code. A value of ``-1`` indicates all ICMP codes for the specified ICMP type.

          

          

        UserIdGroupPairs -> (list)

          

          One or more security group and AWS account ID pairs.

          

          (structure)

            

            Describes a security group and AWS account ID pair. 

            

            UserId -> (string)

              

              The ID of an AWS account. EC2-Classic only.

              

              

            GroupName -> (string)

              

              The name of the security group. In a request, use this parameter for a security group in EC2-Classic or a default VPC only. For a security group in a nondefault VPC, use ``GroupId`` .

              

              

            GroupId -> (string)

              

              The ID of the security group.

              

              

            

          

        IpRanges -> (list)

          

          One or more IP ranges.

          

          (structure)

            

            Describes an IP range.

            

            CidrIp -> (string)

              

              The CIDR range. You can either specify a CIDR range or a source security group, not both.

              

              

            

          

        PrefixListIds -> (list)

          

          (Valid for  authorize-security-group-egress ,  revoke-security-group-egress and  describe-security-groups only) One or more prefix list IDs for an AWS service. In an  authorize-security-group-egress request, this is the AWS service that you want to access through a VPC endpoint from instances associated with the security group.

          

          (structure)

            

            The ID of the prefix.

            

            PrefixListId -> (string)

              

              The ID of the prefix.

              

              

            

          

        

      

    VpcId -> (string)

      

      [EC2-VPC] The ID of the VPC for the security group.

      

      

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

          

          

        

      

    

  



.. _Protocol Numbers: http://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml
.. _Security Groups for Your VPC: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_SecurityGroups.html
.. _Amazon EC2 Security Groups: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html
