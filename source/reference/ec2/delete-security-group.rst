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



========
Synopsis
========

::

    delete-security-group
  [--dry-run | --no-dry-run]
  [--group-name <value>]
  [--group-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--group-name`` (string)


  [EC2-Classic, default VPC] The name of the security group. You can specify either the security group name or the security group ID.

  

``--group-id`` (string)


  The ID of the security group. Required for a nondefault VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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