[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-network-acl-entry:


************************
create-network-acl-entry
************************



===========
Description
===========



Creates an entry (a rule) in a network ACL with the specified rule number. Each network ACL has a set of numbered ingress rules and a separate set of numbered egress rules. When determining whether a packet should be allowed in or out of a subnet associated with the ACL, we process the entries in the ACL according to the rule numbers, in ascending order. Each network ACL has a set of ingress rules and a separate set of egress rules.

 

We recommend that you leave room between the rule numbers (for example, 100, 110, 120, ...), and not number them one right after the other (for example, 101, 102, 103, ...). This makes it easier to add a rule between existing ones without having to renumber the rules.

 

After you add an entry, you can't modify it; you must either replace it, or create an entry and delete the old one.

 

For more information about network ACLs, see `Network ACLs <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateNetworkAclEntry>`_


========
Synopsis
========

::

    create-network-acl-entry
  [--cidr-block <value>]
  [--dry-run | --no-dry-run]
  --egress | --ingress
  [--icmp-type-code <value>]
  [--ipv6-cidr-block <value>]
  --network-acl-id <value>
  [--port-range <value>]
  --protocol <value>
  --rule-action <value>
  --rule-number <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cidr-block`` (string)


  The IPv4 network range to allow or deny, in CIDR notation (for example ``172.16.0.0/24`` ).

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--egress`` | ``--ingress`` (boolean)


  Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet).

  

``--icmp-type-code`` (structure)


  ICMP protocol: The ICMP or ICMPv6 type and code. Required if specifying the ICMP protocol, or protocol 58 (ICMPv6) with an IPv6 CIDR block.

  



Shorthand Syntax::

    Code=integer,Type=integer




JSON Syntax::

  {
    "Code": integer,
    "Type": integer
  }



``--ipv6-cidr-block`` (string)


  The IPv6 network range to allow or deny, in CIDR notation (for example ``2001:db8:1234:1a00::/64`` ).

  

``--network-acl-id`` (string)


  The ID of the network ACL.

  

``--port-range`` (structure)


  TCP or UDP protocols: The range of ports the rule applies to.

  



Shorthand Syntax::

    From=integer,To=integer




JSON Syntax::

  {
    "From": integer,
    "To": integer
  }



``--protocol`` (string)


  The protocol. A value of ``-1`` or ``all`` means all protocols. If you specify ``all`` , ``-1`` , or a protocol number other than ``tcp`` , ``udp`` , or ``icmp`` , traffic on all ports is allowed, regardless of any ports or ICMP types or codes you specify. If you specify protocol ``58`` (ICMPv6) and specify an IPv4 CIDR block, traffic for all ICMP types and codes allowed, regardless of any that you specify. If you specify protocol ``58`` (ICMPv6) and specify an IPv6 CIDR block, you must specify an ICMP type and code.

  

``--rule-action`` (string)


  Indicates whether to allow or deny the traffic that matches the rule.

  

  Possible values:

  
  *   ``allow``

  
  *   ``deny``

  

  

``--rule-number`` (integer)


  The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.

   

  Constraints: Positive integer from 1 to 32766. The range 32767 to 65535 is reserved for internal use.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a network ACL entry**

This example creates an entry for the specified network ACL. The rule allows ingress traffic from any IPv4 address (0.0.0.0/0) on UDP port 53 (DNS) into any associated subnet. If the command succeeds, no output is returned.

Command::

  aws ec2 create-network-acl-entry --network-acl-id acl-5fb85d36 --ingress --rule-number 100 --protocol udp --port-range From=53,To=53 --cidr-block 0.0.0.0/0 --rule-action allow


This example creates a rule for the specified network ACL that allows ingress traffic from any IPv6 address (::/0) on TCP port 80 (HTTP).

Command::

  aws ec2 create-network-acl-entry --network-acl-id acl-5fb85d36 --ingress --rule-number 120 --protocol tcp --port-range From=80,To=80 --ipv6-cidr-block ::/0 --rule-action allow

======
Output
======

None