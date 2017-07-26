[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-route-table:


******************
delete-route-table
******************



===========
Description
===========



Deletes the specified route table. You must disassociate the route table from any subnets before you can delete it. You can't delete the main route table.



========
Synopsis
========

::

    delete-route-table
  [--dry-run | --no-dry-run]
  --route-table-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--route-table-id`` (string)


  The ID of the route table.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a route table**

This example deletes the specified route table. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-route-table --route-table-id rtb-22574640


======
Output
======

None