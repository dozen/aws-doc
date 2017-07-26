[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 associate-dhcp-options:


**********************
associate-dhcp-options
**********************



===========
Description
===========



Associates a set of DHCP options (that you've previously created) with the specified VPC, or associates no DHCP options with the VPC.

 

After you associate the options with the VPC, any existing instances and all new instances that you launch in that VPC use the options. You don't need to restart or relaunch the instances. They automatically pick up the changes within a few hours, depending on how frequently the instance renews its DHCP lease. You can explicitly renew the lease using the operating system on the instance.

 

For more information, see `DHCP Options Sets`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    associate-dhcp-options
  [--dry-run | --no-dry-run]
  --dhcp-options-id <value>
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--dhcp-options-id`` (string)


  The ID of the DHCP options set, or ``default`` to associate no DHCP options with the VPC.

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To associate a DHCP options set with your VPC**

This example associates the specified DHCP options set with the specified VPC. If the command succeeds, no output is returned.

Command::

  aws ec2 associate-dhcp-options --dhcp-options-id dopt-d9070ebb --vpc-id vpc-a01106c2

**To associate the default DHCP options set with your VPC**

This example associates the default DHCP options set with the specified VPC. If the command succeeds, no output is returned.

Command::

  aws ec2 associate-dhcp-options --dhcp-options-id default --vpc-id vpc-a01106c2


======
Output
======

None

.. _DHCP Options Sets: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_DHCP_Options.html
