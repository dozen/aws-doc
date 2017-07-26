[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 detach-classic-link-vpc:


***********************
detach-classic-link-vpc
***********************



===========
Description
===========



Unlinks (detaches) a linked EC2-Classic instance from a VPC. After the instance has been unlinked, the VPC security groups are no longer associated with it. An instance is automatically unlinked from a VPC when it's stopped.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DetachClassicLinkVpc>`_


========
Synopsis
========

::

    detach-classic-link-vpc
  [--dry-run | --no-dry-run]
  --instance-id <value>
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the instance to unlink from the VPC.

  

``--vpc-id`` (string)


  The ID of the VPC to which the instance is linked.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To unlink (detach) an EC2-Classic instance from a VPC**

This example unlinks instance i-0598c7d356eba48d7 from VPC vpc-88888888.

Command::

  aws ec2 detach-classic-link-vpc --instance-id i-0598c7d356eba48d7 --vpc-id vpc-88888888

Output::

  {
    "Return": true
  }

======
Output
======

Return -> (boolean)

  

  Returns ``true`` if the request succeeds; otherwise, it returns an error.

  

  

