[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 disassociate-route-table:


************************
disassociate-route-table
************************



===========
Description
===========



Disassociates a subnet from a route table.

 

After you perform this action, the subnet no longer uses the routes in the route table. Instead, it uses the routes in the VPC's main route table. For more information about route tables, see `Route Tables`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    disassociate-route-table
  [--dry-run | --no-dry-run]
  --association-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--association-id`` (string)


  The association ID representing the current association between the route table and subnet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To disassociate a route table**

This example disassociates the specified route table from the specified subnet. If the command succeeds, no output is returned.

Command::

  aws ec2 disassociate-route-table --association-id rtbassoc-781d0d1a


======
Output
======

None

.. _Route Tables: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html
