[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 revoke-security-group-ingress:


*****************************
revoke-security-group-ingress
*****************************





.. note::

  To specify multiple rules in a single command use the ``--ip-permissions`` option



===========
Description
===========



Removes one or more ingress rules from a security group. The values that you specify in the revoke request (for example, ports) must match the existing rule's values for the rule to be removed.

 

Each rule consists of the protocol and the CIDR range or source security group. For the TCP and UDP protocols, you must also specify the destination port or range of ports. For the ICMP protocol, you must also specify the ICMP type and code.

 

Rule changes are propagated to instances within the security group as quickly as possible. However, a small delay might occur.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/RevokeSecurityGroupIngress>`_


========
Synopsis
========

::

    revoke-security-group-ingress
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


  The ID of the security group. Required for a security group in a nondefault VPC.

  

``--group-name`` (string)


  [EC2-Classic, default VPC] The name of the security group.

  

``--ip-permissions`` (list)


  A set of IP permissions. You can't specify a source security group and a CIDR IP address range.

  



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

**To remove a rule from a security group**

This example removes TCP port 22 access for the ``203.0.113.0/24`` address range from the security group named ``MySecurityGroup``. If the command succeeds, no output is returned.

Command::

  aws ec2 revoke-security-group-ingress --group-name MySecurityGroup --protocol tcp --port 22 --cidr 203.0.113.0/24

**[EC2-VPC] To remove a rule using the IP permissions set**

This example uses the ``ip-permissions`` parameter to remove an inbound rule that allows the ICMP message ``Destination Unreachable: Fragmentation Needed and Don't Fragment was Set`` (Type 3, Code 4). If the command succeeds, no output is returned. For more information about quoting JSON-formatted parameters, see `Quoting Strings`_.

Command::

  aws ec2 revoke-security-group-ingress --group-id sg-123abc12 --ip-permissions '[{"IpProtocol": "icmp", "FromPort": 3, "ToPort": 4, "IpRanges": [{"CidrIp": "0.0.0.0/0"}]}]' 

.. _`Quoting Strings`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-param.html#quoting-strings

======
Output
======

None