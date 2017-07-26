[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 associate-route-table:


*********************
associate-route-table
*********************



===========
Description
===========



Associates a subnet with a route table. The subnet and route table must be in the same VPC. This association causes traffic originating from the subnet to be routed according to the routes in the route table. The action returns an association ID, which you need in order to disassociate the route table from the subnet later. A route table can be associated with multiple subnets.

 

For more information about route tables, see `Route Tables`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    associate-route-table
  [--dry-run | --no-dry-run]
  --subnet-id <value>
  --route-table-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--subnet-id`` (string)


  The ID of the subnet.

  

``--route-table-id`` (string)


  The ID of the route table.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To associate a route table with a subnet**

This example associates the specified route table with the specified subnet.

Command::

  aws ec2 associate-route-table --route-table-id rtb-22574640 --subnet-id subnet-9d4a7b6c

Output::

  {
      "AssociationId": "rtbassoc-781d0d1a"
  }

======
Output
======

AssociationId -> (string)

  

  The route table association ID (needed to disassociate the route table).

  

  



.. _Route Tables: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html
