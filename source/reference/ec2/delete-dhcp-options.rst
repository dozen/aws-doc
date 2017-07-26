[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-dhcp-options:


*******************
delete-dhcp-options
*******************



===========
Description
===========



Deletes the specified set of DHCP options. You must disassociate the set of DHCP options before you can delete it. You can disassociate the set of DHCP options by associating either a new set of options or the default set of options with the VPC.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DeleteDhcpOptions>`_


========
Synopsis
========

::

    delete-dhcp-options
  --dhcp-options-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dhcp-options-id`` (string)


  The ID of the DHCP options set.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a DHCP options set**

This example deletes the specified DHCP options set. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-dhcp-options --dhcp-options-id dopt-d9070ebb


======
Output
======

None