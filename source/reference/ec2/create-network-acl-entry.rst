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

 

For more information about network ACLs, see `Network ACLs`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    create-network-acl-entry
  [--dry-run | --no-dry-run]
  --network-acl-id <value>
  --rule-number <value>
  --protocol <value>
  --rule-action <value>
  --egress | --ingress
  --cidr-block <value>
  [--icmp-type-code <value>]
  [--port-range <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--network-acl-id`` (string)


  The ID of the network ACL.

  

``--rule-number`` (integer)


  The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.

   

  Constraints: Positive integer from 1 to 32766

  

``--protocol`` (string)


  The protocol. A value of -1 means all protocols.

  

``--rule-action`` (string)


  Indicates whether to allow or deny the traffic that matches the rule.

  

  Possible values:

  
  *   ``allow``

  
  *   ``deny``

  

  

``--egress`` | ``--ingress`` (boolean)


  Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet).

  

``--cidr-block`` (string)


  The network range to allow or deny, in CIDR notation (for example ``172.16.0.0/24`` ).

  

``--icmp-type-code`` (structure)


  ICMP protocol: The ICMP type and code. Required if specifying ICMP for the protocol.

  



Shorthand Syntax::

    Type=integer,Code=integer




JSON Syntax::

  {
    "Type": integer,
    "Code": integer
  }



``--port-range`` (structure)


  TCP or UDP protocols: The range of ports the rule applies to.

  



Shorthand Syntax::

    From=integer,To=integer




JSON Syntax::

  {
    "From": integer,
    "To": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a network ACL entry**

This example creates an entry for the specified network ACL. The rule allows ingress traffic from anywhere (0.0.0.0/0) on UDP port 53 (DNS) into any associated subnet. If the command succeeds, no output is returned.

Command::

  aws ec2 create-network-acl-entry --network-acl-id acl-5fb85d36 --ingress --rule-number 100 --protocol udp --port-range From=53,To=53 --cidr-block 0.0.0.0/0 --rule-action allow


======
Output
======

None

.. _Network ACLs: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html
