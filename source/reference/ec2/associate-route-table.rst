[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 associate-route-table:


*********************
associate-route-table
*********************



===========
Description
===========



Associates a subnet with a route table. The subnet and route table must be in the same VPC. This association causes traffic originating from the subnet to be routed according to the routes in the route table. The action returns an association ID, which you need in order to disassociate the route table from the subnet later. A route table can be associated with multiple subnets.

 

For more information about route tables, see `Route Tables <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AssociateRouteTable>`_


========
Synopsis
========

::

    associate-route-table
  [--dry-run | --no-dry-run]
  --route-table-id <value>
  --subnet-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--route-table-id`` (string)


  The ID of the route table.

  

``--subnet-id`` (string)


  The ID of the subnet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

