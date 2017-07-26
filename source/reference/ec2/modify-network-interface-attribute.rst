[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-network-interface-attribute:


**********************************
modify-network-interface-attribute
**********************************



===========
Description
===========



Modifies the specified network interface attribute. You can specify only one attribute at a time.



========
Synopsis
========

::

    modify-network-interface-attribute
  [--dry-run | --no-dry-run]
  --network-interface-id <value>
  [--description <value>]
  [--source-dest-check | --no-source-dest-check]
  [--groups <value>]
  [--attachment <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--network-interface-id`` (string)


  The ID of the network interface.

  

``--description`` (structure)


  A description for the network interface.

  

``--source-dest-check`` | ``--no-source-dest-check`` (structure)


  Indicates whether source/destination checking is enabled. A value of ``true`` means checking is enabled, and ``false`` means checking is disabled. This value must be ``false`` for a NAT instance to perform NAT. For more information, see `NAT Instances`_ in the *Amazon Virtual Private Cloud User Guide* .

  

``--groups`` (list)


  Changes the security groups for the network interface. The new set of groups you specify replaces the current set. You must specify at least one group, even if it's just the default security group in the VPC. You must specify the ID of the security group, not the name.

  



Syntax::

  "string" "string" ...



``--attachment`` (structure)


  Information about the interface attachment. If modifying the 'delete on termination' attribute, you must specify the ID of the interface attachment.

  



Shorthand Syntax::

    AttachmentId=string,DeleteOnTermination=boolean




JSON Syntax::

  {
    "AttachmentId": "string",
    "DeleteOnTermination": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To modify the attachment attribute of a network interface**

This example command modifies the ``attachment`` attribute of the specified network interface.

Command::

  aws ec2 modify-network-interface-attribute --network-interface-id eni-686ea200 --attachment AttachmentId=eni-attach-43348162,DeleteOnTermination=false


**To modify the description attribute of a network interface**

This example command modifies the ``description`` attribute of the specified network interface.

Command::

  aws ec2 modify-network-interface-attribute --network-interface-id eni-686ea200 --description "My description"
  

**To modify the groupSet attribute of a network interface**

This example command modifies the ``groupSet`` attribute of the specified network interface.

Command::

  aws ec2 modify-network-interface-attribute --network-interface-id eni-686ea200 --groups sg-903004f8 sg-1a2b3c4d
  

**To modify the sourceDestCheck attribute of a network interface**

This example command modifies the ``sourceDestCheck`` attribute of the specified network interface.

Command::

  aws ec2 modify-network-interface-attribute --network-interface-id eni-686ea200 --no-source-dest-check


======
Output
======

None

.. _NAT Instances: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_NAT_Instance.html
