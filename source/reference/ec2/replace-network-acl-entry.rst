[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 replace-network-acl-entry:


*************************
replace-network-acl-entry
*************************



===========
Description
===========



Replaces an entry (rule) in a network ACL. For more information about network ACLs, see `Network ACLs`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    replace-network-acl-entry
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


  The ID of the ACL.

  

``--rule-number`` (integer)


  The rule number of the entry to replace.

  

``--protocol`` (string)


  The IP protocol. You can specify ``all`` or ``-1`` to mean all protocols.

  

``--rule-action`` (string)


  Indicates whether to allow or deny the traffic that matches the rule.

  

  Possible values:

  
  *   ``allow``

  
  *   ``deny``

  

  

``--egress`` | ``--ingress`` (boolean)


  Indicates whether to replace the egress rule.

   

  Default: If no value is specified, we replace the ingress rule.

  

``--cidr-block`` (string)


  The network range to allow or deny, in CIDR notation.

  

``--icmp-type-code`` (structure)


  ICMP protocol: The ICMP type and code. Required if specifying 1 (ICMP) for the protocol.

  



Shorthand Syntax::

    Type=integer,Code=integer




JSON Syntax::

  {
    "Type": integer,
    "Code": integer
  }



``--port-range`` (structure)


  TCP or UDP protocols: The range of ports the rule applies to. Required if specifying 6 (TCP) or 17 (UDP) for the protocol.

  



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

**To replace a network ACL entry**

This example replaces an entry for the specified network ACL. The new rule 100 allows ingress traffic from 203.0.113.12/24 on UDP port 53 (DNS) into any associated subnet.

Command::

  aws ec2 replace-network-acl-entry --network-acl-id acl-5fb85d36 --ingress --rule-number 100 --protocol udp --port-range From=53,To=53 --cidr-block 203.0.113.12/24 --rule-action allow


======
Output
======

None

.. _Network ACLs: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html
