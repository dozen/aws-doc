[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 attach-classic-link-vpc:


***********************
attach-classic-link-vpc
***********************



===========
Description
===========



Links an EC2-Classic instance to a ClassicLink-enabled VPC through one or more of the VPC's security groups. You cannot link an EC2-Classic instance to more than one VPC at a time. You can only link an instance that's in the ``running`` state. An instance is automatically unlinked from a VPC when it's stopped - you can link it to the VPC again when you restart it.

 

After you've linked an instance, you cannot change the VPC security groups that are associated with it. To change the security groups, you must first unlink the instance, and then link it again.

 

Linking your instance to a VPC is sometimes referred to as *attaching* your instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AttachClassicLinkVpc>`_


========
Synopsis
========

::

    attach-classic-link-vpc
  [--dry-run | --no-dry-run]
  --groups <value>
  --instance-id <value>
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--groups`` (list)


  The ID of one or more of the VPC's security groups. You cannot specify security groups from a different VPC.

  



Syntax::

  "string" "string" ...



``--instance-id`` (string)


  The ID of an EC2-Classic instance to link to the ClassicLink-enabled VPC.

  

``--vpc-id`` (string)


  The ID of a ClassicLink-enabled VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To link (attach) an EC2-Classic instance to a VPC**

This example links instance i-1234567890abcdef0 to VPC vpc-88888888 through the VPC security group sg-12312312.

Command::

  aws ec2 attach-classic-link-vpc --instance-id  i-1234567890abcdef0 --vpc-id vpc-88888888 --groups sg-12312312

Output::

  {
    "Return": true
  }

======
Output
======

Return -> (boolean)

  

  Returns ``true`` if the request succeeds; otherwise, it returns an error.

  

  

