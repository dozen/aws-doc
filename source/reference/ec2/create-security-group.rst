[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-security-group:


*********************
create-security-group
*********************



===========
Description
===========



Creates a security group.

 

A security group is for use with instances either in the EC2-Classic platform or in a specific VPC. For more information, see `Amazon EC2 Security Groups <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html>`_ in the *Amazon Elastic Compute Cloud User Guide* and `Security Groups for Your VPC <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_SecurityGroups.html>`_ in the *Amazon Virtual Private Cloud User Guide* .

 

.. warning::

   

  EC2-Classic: You can have up to 500 security groups.

   

  EC2-VPC: You can create up to 500 security groups per VPC.

   

 

When you create a security group, you specify a friendly name of your choice. You can have a security group for use in EC2-Classic with the same name as a security group for use in a VPC. However, you can't have two security groups for use in EC2-Classic with the same name or two security groups for use in a VPC with the same name.

 

You have a default security group for use in EC2-Classic and a default security group for use in your VPC. If you don't specify a security group when you launch an instance, the instance is launched into the appropriate default security group. A default security group includes a default rule that grants instances unrestricted network access to each other.

 

You can add or remove rules from your security groups using  authorize-security-group-ingress ,  authorize-security-group-egress ,  revoke-security-group-ingress , and  revoke-security-group-egress .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateSecurityGroup>`_


========
Synopsis
========

::

    create-security-group
  --description <value>
  --group-name <value>
  [--vpc-id <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--description`` (string)


  A description for the security group. This is informational only.

   

  Constraints: Up to 255 characters in length

   

  Constraints for EC2-Classic: ASCII characters

   

  Constraints for EC2-VPC: a-z, A-Z, 0-9, spaces, and ._-:/()#,@[]+=;{}!$*

  

``--group-name`` (string)


  The name of the security group.

   

  Constraints: Up to 255 characters in length

   

  Constraints for EC2-Classic: ASCII characters

   

  Constraints for EC2-VPC: a-z, A-Z, 0-9, spaces, and ._-:/()#,@[]+=;{}!$*

  

``--vpc-id`` (string)


  [EC2-VPC] The ID of the VPC. Required for EC2-VPC.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a security group for EC2-Classic**

This example creates a security group named ``MySecurityGroup``.

Command::

  aws ec2 create-security-group --group-name MySecurityGroup --description "My security group"

Output::

  {
      "GroupId": "sg-903004f8"
  }

**To create a security group for EC2-VPC**

This example creates a security group named ``MySecurityGroup`` for the specified VPC.

Command::

  aws ec2 create-security-group --group-name MySecurityGroup --description "My security group" --vpc-id vpc-1a2b3c4d

Output::

  {
      "GroupId": "sg-903004f8"
  }

For more information, see `Using Security Groups`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Security Groups`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-sg.html


======
Output
======

GroupId -> (string)

  

  The ID of the security group.

  

  

