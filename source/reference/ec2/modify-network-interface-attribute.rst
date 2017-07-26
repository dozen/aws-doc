[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-network-interface-attribute:


**********************************
modify-network-interface-attribute
**********************************



===========
Description
===========



Modifies the specified network interface attribute. You can specify only one attribute at a time.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifyNetworkInterfaceAttribute>`_


========
Synopsis
========

::

    modify-network-interface-attribute
  [--attachment <value>]
  [--description <value>]
  [--dry-run | --no-dry-run]
  [--groups <value>]
  --network-interface-id <value>
  [--source-dest-check | --no-source-dest-check]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attachment`` (structure)


  Information about the interface attachment. If modifying the 'delete on termination' attribute, you must specify the ID of the interface attachment.

  



Shorthand Syntax::

    AttachmentId=string,DeleteOnTermination=boolean




JSON Syntax::

  {
    "AttachmentId": "string",
    "DeleteOnTermination": true|false
  }



``--description`` (structure)


  A description for the network interface.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--groups`` (list)


  Changes the security groups for the network interface. The new set of groups you specify replaces the current set. You must specify at least one group, even if it's just the default security group in the VPC. You must specify the ID of the security group, not the name.

  



Syntax::

  "string" "string" ...



``--network-interface-id`` (string)


  The ID of the network interface.

  

``--source-dest-check`` | ``--no-source-dest-check`` (structure)


  Indicates whether source/destination checking is enabled. A value of ``true`` means checking is enabled, and ``false`` means checking is disabled. This value must be ``false`` for a NAT instance to perform NAT. For more information, see `NAT Instances <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_NAT_Instance.html>`_ in the *Amazon Virtual Private Cloud User Guide* .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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