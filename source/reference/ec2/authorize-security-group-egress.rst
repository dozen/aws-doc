[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 authorize-security-group-egress:


*******************************
authorize-security-group-egress
*******************************





.. note::

  To specify multiple rules in a single command use the ``--ip-permissions`` option



===========
Description
===========



[EC2-VPC only] Adds one or more egress rules to a security group for use with a VPC. Specifically, this action permits instances to send traffic to one or more destination IPv4 or IPv6 CIDR address ranges, or to one or more destination security groups for the same VPC. This action doesn't apply to security groups for use in EC2-Classic. For more information, see `Security Groups for Your VPC <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_SecurityGroups.html>`_ in the *Amazon Virtual Private Cloud User Guide* . For more information about security group limits, see `Amazon VPC Limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Appendix_Limits.html>`_ .

 

Each rule consists of the protocol (for example, TCP), plus either a CIDR range or a source group. For the TCP and UDP protocols, you must also specify the destination port or port range. For the ICMP protocol, you must also specify the ICMP type and code. You can use -1 for the type or code to mean all types or all codes.

 

Rule changes are propagated to affected instances as quickly as possible. However, a small delay might occur.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AuthorizeSecurityGroupEgress>`_


========
Synopsis
========

::

    authorize-security-group-egress
  [--dry-run | --no-dry-run]
  --group-id <value>
  [--ip-permissions <value>]
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

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--group-id`` (string)


  The ID of the security group.

  

``--ip-permissions`` (list)


  A set of IP permissions. You can't specify a destination security group and a CIDR IP address range.

  



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

**To add a rule that allows outbound traffic to a specific address range**

This example command adds a rule that grants access to the specified address ranges on TCP port 80.

Command::

  aws ec2 authorize-security-group-egress --group-id sg-1a2b3c4d --ip-permissions '[{"IpProtocol": "tcp", "FromPort": 80, "ToPort": 80, "IpRanges": [{"CidrIp": "10.0.0.0/16"}]}]'

**To add a rule that allows outbound traffic to a specific security group**

This example command adds a rule that grants access to the specified security group on TCP port 80.

Command::

  aws ec2 authorize-security-group-egress --group-id sg-1a2b3c4d --ip-permissions '[{"IpProtocol": "tcp", "FromPort": 80, "ToPort": 80, "UserIdGroupPairs": [{"GroupId": "sg-4b51a32f"}]}]' 


======
Output
======

None