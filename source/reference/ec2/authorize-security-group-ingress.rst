[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 authorize-security-group-ingress:


********************************
authorize-security-group-ingress
********************************





.. note::

  To specify multiple rules in a single command use the ``--ip-permissions`` option



===========
Description
===========



Adds one or more ingress rules to a security group.

 

Rule changes are propagated to instances within the security group as quickly as possible. However, a small delay might occur.

 

[EC2-Classic] This action gives one or more IPv4 CIDR address ranges permission to access a security group in your account, or gives one or more security groups (called the *source groups* ) permission to access a security group for your account. A source group can be for your own AWS account, or another. You can have up to 100 rules per group.

 

[EC2-VPC] This action gives one or more IPv4 or IPv6 CIDR address ranges permission to access a security group in your VPC, or gives one or more other security groups (called the *source groups* ) permission to access a security group for your VPC. The security groups must all be for the same VPC or a peer VPC in a VPC peering connection. For more information about VPC security group limits, see `Amazon VPC Limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Appendix_Limits.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AuthorizeSecurityGroupIngress>`_


========
Synopsis
========

::

    authorize-security-group-ingress
  [--group-id <value>]
  [--group-name <value>]
  [--ip-permissions <value>]
  [--dry-run | --no-dry-run]
  [--protocol <value>]
  [--port <value>]
  [--cidr <value>]
  [--source-group <value>]
  [--group-owner <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--group-id`` (string)


  The ID of the security group. Required for a nondefault VPC.

  

``--group-name`` (string)


  [EC2-Classic, default VPC] The name of the security group.

  

``--ip-permissions`` (list)


  A set of IP permissions. Can be used to specify multiple rules in a single command.

  



Shorthand Syntax::

    FromPort=integer,IpProtocol=string,IpRanges=[{CidrIp=string},{CidrIp=string}],Ipv6Ranges=[{CidrIpv6=string},{CidrIpv6=string}],PrefixListIds=[{PrefixListId=string},{PrefixListId=string}],ToPort=integer,UserIdGroupPairs=[{GroupId=string,GroupName=string,PeeringStatus=string,UserId=string,VpcId=string,VpcPeeringConnectionId=string},{GroupId=string,GroupName=string,PeeringStatus=string,UserId=string,VpcId=string,VpcPeeringConnectionId=string}] ...




JSON Syntax::

  [
    {
      "FromPort": integer,
      "IpProtocol": "string",
      "IpRanges": [
        {
          "CidrIp": "string"
        }
        ...
      ],
      "Ipv6Ranges": [
        {
          "CidrIpv6": "string"
        }
        ...
      ],
      "PrefixListIds": [
        {
          "PrefixListId": "string"
        }
        ...
      ],
      "ToPort": integer,
      "UserIdGroupPairs": [
        {
          "GroupId": "string",
          "GroupName": "string",
          "PeeringStatus": "string",
          "UserId": "string",
          "VpcId": "string",
          "VpcPeeringConnectionId": "string"
        }
        ...
      ]
    }
    ...
  ]



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--protocol`` (string)


  The IP protocol: ``tcp`` | ``udp`` | ``icmp`` 

   

  (VPC only) Use ``all`` to specify all protocols.

  

  If this argument is provided without also providing the ``port`` argument, then it will be applied to all ports for the specified protocol.

  

``--port`` (string)


  For TCP or UDP: The range of ports to allow. A single integer or a range (``min-max`` ).

  

  For ICMP: A single integer or a range (``type-code`` ) representing the ICMP type number and the ICMP code number respectively. A value of -1 indicates all ICMP codes for all ICMP types. A value of -1 just for ``type`` indicates all ICMP codes for the specified ICMP type.

  

``--cidr`` (string)


  The CIDR IP range.

  

``--source-group`` (string)


  The name or ID of the source security group. Cannot be used when specifying a CIDR IP address.

  

``--group-owner`` (string)


  The AWS account ID that owns the source security group. Cannot be used when specifying a CIDR IP address.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**[EC2-Classic] To add a rule that allows inbound SSH traffic**

This example enables inbound traffic on TCP port 22 (SSH). If the command succeeds, no output is returned.

Command::

  aws ec2 authorize-security-group-ingress --group-name MySecurityGroup --protocol tcp --port 22 --cidr 203.0.113.0/24

**[EC2-Classic] To add a rule that allows inbound HTTP traffic from a security group in another account**

This example enables inbound traffic on TCP port 80 from a source security group (otheraccountgroup) in a different AWS account (123456789012). If the command succeeds, no output is returned.

Command::

  aws ec2 authorize-security-group-ingress --group-name MySecurityGroup --protocol tcp --port 80 --source-group otheraccountgroup --group-owner 123456789012

**[EC2-Classic] To add a rule that allows inbound HTTPS traffic from an ELB**

This example enables inbound traffic on TCP port 443 from an ELB. If the command succeeds, no output is returned.

Command::

  aws ec2 authorize-security-group-ingress --group-name MySecurityGroup --protocol tcp --port 443 --source-group amazon-elb-sg --group-owner amazon-elb

**[EC2-VPC] To add a rule that allows inbound SSH traffic**

This example enables inbound traffic on TCP port 22 (SSH). Note that you can't reference a security group for EC2-VPC by name. If the command succeeds, no output is returned.

Command::

  aws ec2 authorize-security-group-ingress --group-id sg-903004f8 --protocol tcp --port 22 --cidr 203.0.113.0/24

**[EC2-VPC] To add a rule that allows inbound HTTP traffic from another security group**

This example enables inbound access on TCP port 80 from the source security group sg-1a2b3c4d. Note that for EC2-VPC, the source group must be in the same VPC or in a peer VPC (requires a VPC peering connection). If the command succeeds, no output is returned.

Command::

  aws ec2 authorize-security-group-ingress --group-id sg-111aaa22 --protocol tcp --port 80 --source-group sg-1a2b3c4d

**[EC2-VPC] To add a custom ICMP rule**

This example uses the ``ip-permissions`` parameter to add an inbound rule that allows the ICMP message ``Destination Unreachable: Fragmentation Needed and Don't Fragment was Set`` (Type 3, Code 4) from anywhere. If the command succeeds, no output is returned. For more information about quoting JSON-formatted parameters, see `Quoting Strings`_.

Command::

  aws ec2 authorize-security-group-ingress --group-id sg-123abc12 --ip-permissions '[{"IpProtocol": "icmp", "FromPort": 3, "ToPort": 4, "IpRanges": [{"CidrIp": "0.0.0.0/0"}]}]' 

**[EC2-VPC] To add a rule for IPv6 traffic**

This example grants SSH access (port 22) from the IPv6 range ``2001:db8:1234:1a00::/64``.

Command::

  aws ec2 authorize-security-group-ingress --group-id sg-9bf6ceff --ip-permissions '[{"IpProtocol": "tcp", "FromPort": 22, "ToPort": 22, "Ipv6Ranges": [{"CidrIpv6": "2001:db8:1234:1a00::/64"}]}]'

For more information, see `Using Security Groups`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Security Groups`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-sg.html
.. _`Quoting Strings`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-param.html#quoting-strings


======
Output
======

None