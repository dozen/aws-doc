[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-security-group:


*********************
delete-security-group
*********************



===========
Description
===========



Deletes a security group.

 

If you attempt to delete a security group that is associated with an instance, or is referenced by another security group, the operation fails with ``InvalidGroup.InUse`` in EC2-Classic or ``DependencyViolation`` in EC2-VPC.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DeleteSecurityGroup>`_


========
Synopsis
========

::

    delete-security-group
  [--group-id <value>]
  [--group-name <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--group-id`` (string)


  The ID of the security group. Required for a nondefault VPC.

  

``--group-name`` (string)


  [EC2-Classic, default VPC] The name of the security group. You can specify either the security group name or the security group ID.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**[EC2-Classic] To delete a security group**

This example deletes the security group named ``MySecurityGroup``. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-security-group --group-name MySecurityGroup

**[EC2-VPC] To delete a security group**

This example deletes the security group with the ID ``sg-903004f8``. Note that you can't reference a security group for EC2-VPC by name. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-security-group --group-id sg-903004f8

For more information, see `Using Security Groups`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Security Groups`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-sg.html


======
Output
======

None