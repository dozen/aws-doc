[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 replace-network-acl-entry:


*************************
replace-network-acl-entry
*************************



===========
Description
===========



Replaces an entry (rule) in a network ACL. For more information about network ACLs, see `Network ACLs <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ReplaceNetworkAclEntry>`_


========
Synopsis
========

::

    replace-network-acl-entry
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


  Indicates whether to replace the egress rule.

   

  Default: If no value is specified, we replace the ingress rule.

  

``--icmp-type-code`` (structure)


  ICMP protocol: The ICMP or ICMPv6 type and code. Required if specifying the ICMP (1) protocol, or protocol 58 (ICMPv6) with an IPv6 CIDR block.

  



Shorthand Syntax::

    Code=integer,Type=integer




JSON Syntax::

  {
    "Code": integer,
    "Type": integer
  }



``--ipv6-cidr-block`` (string)


  The IPv6 network range to allow or deny, in CIDR notation (for example ``2001:bd8:1234:1a00::/64`` ).

  

``--network-acl-id`` (string)


  The ID of the ACL.

  

``--port-range`` (structure)


  TCP or UDP protocols: The range of ports the rule applies to. Required if specifying TCP (6) or UDP (17) for the protocol.

  



Shorthand Syntax::

    From=integer,To=integer




JSON Syntax::

  {
    "From": integer,
    "To": integer
  }



``--protocol`` (string)


  The IP protocol. You can specify ``all`` or ``-1`` to mean all protocols. If you specify ``all`` , ``-1`` , or a protocol number other than ``tcp`` , ``udp`` , or ``icmp`` , traffic on all ports is allowed, regardless of any ports or ICMP types or codes you specify. If you specify protocol ``58`` (ICMPv6) and specify an IPv4 CIDR block, traffic for all ICMP types and codes allowed, regardless of any that you specify. If you specify protocol ``58`` (ICMPv6) and specify an IPv6 CIDR block, you must specify an ICMP type and code.

  

``--rule-action`` (string)


  Indicates whether to allow or deny the traffic that matches the rule.

  

  Possible values:

  
  *   ``allow``

  
  *   ``deny``

  

  

``--rule-number`` (integer)


  The rule number of the entry to replace.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To replace a network ACL entry**

This example replaces an entry for the specified network ACL. The new rule 100 allows ingress traffic from 203.0.113.12/24 on UDP port 53 (DNS) into any associated subnet.

Command::

  aws ec2 replace-network-acl-entry --network-acl-id acl-5fb85d36 --ingress --rule-number 100 --protocol udp --port-range From=53,To=53 --cidr-block 203.0.113.12/24 --rule-action allow


======
Output
======

None