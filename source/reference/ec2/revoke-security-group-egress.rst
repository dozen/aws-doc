[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 revoke-security-group-egress:


****************************
revoke-security-group-egress
****************************



===========
Description
===========



[EC2-VPC only] Removes one or more egress rules from a security group for EC2-VPC. This action doesn't apply to security groups for use in EC2-Classic. The values that you specify in the revoke request (for example, ports) must match the existing rule's values for the rule to be revoked.

 

Each rule consists of the protocol and the CIDR range or source security group. For the TCP and UDP protocols, you must also specify the destination port or range of ports. For the ICMP protocol, you must also specify the ICMP type and code.

 

Rule changes are propagated to instances within the security group as quickly as possible. However, a small delay might occur.



========
Synopsis
========

::

    revoke-security-group-egress
  [--dry-run | --no-dry-run]
  --group-id <value>
  [--ip-permissions <value>]
  [--protocol <value>]
  [--port <value>]
  [--cidr <value>]
  [--source-group <value>]
  [--group-owner <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

    IpProtocol=string,FromPort=integer,ToPort=integer,UserIdGroupPairs=[{UserId=string,GroupName=string,GroupId=string},{UserId=string,GroupName=string,GroupId=string}],IpRanges=[{CidrIp=string},{CidrIp=string}],PrefixListIds=[{PrefixListId=string},{PrefixListId=string}] ...




JSON Syntax::

  [
    {
      "IpProtocol": "string",
      "FromPort": integer,
      "ToPort": integer,
      "UserIdGroupPairs": [
        {
          "UserId": "string",
          "GroupName": "string",
          "GroupId": "string"
        }
        ...
      ],
      "IpRanges": [
        {
          "CidrIp": "string"
        }
        ...
      ],
      "PrefixListIds": [
        {
          "PrefixListId": "string"
        }
        ...
      ]
    }
    ...
  ]



``--protocol`` (string)


  The IP protocol of this permission.

  

  Valid protocol values: ``tcp`` , ``udp`` , ``icmp`` 

  

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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To remove the rule that allows outbound traffic to a specific address range**

This example command removes the rule that grants access to the specified address ranges on TCP port 80.

Command::

  aws ec2 revoke-security-group-egress --group-id sg-1a2b3c4d --ip-permissions '[{"IpProtocol": "tcp", "FromPort": 80, "ToPort": 80, "IpRanges": [{"CidrIp": "10.0.0.0/16"}]}]'

**To remove the rule that allows outbound traffic to a specific security group**

This example command removes the rule that grants access to the specified security group on TCP port 80.

Command::

  aws ec2 revoke-security-group-egress --group-id sg-1a2b3c4d --ip-permissions '[{"IpProtocol": "tcp", "FromPort": 80, "ToPort": 80, "UserIdGroupPairs": [{"GroupId": "sg-4b51a32f"}]}]' 


======
Output
======

None