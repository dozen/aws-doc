[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 replace-route-table-association:


*******************************
replace-route-table-association
*******************************



===========
Description
===========



Changes the route table associated with a given subnet in a VPC. After the operation completes, the subnet uses the routes in the new route table it's associated with. For more information about route tables, see `Route Tables`_ in the *Amazon Virtual Private Cloud User Guide* .

 

You can also use replace-route-table-association to change which table is the main route table in the VPC. You just specify the main route table's association ID and the route table to be the new main route table.



========
Synopsis
========

::

    replace-route-table-association
  [--dry-run | --no-dry-run]
  --association-id <value>
  --route-table-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--association-id`` (string)


  The association ID.

  

``--route-table-id`` (string)


  The ID of the new route table to associate with the subnet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To replace the route table associated with a subnet**

This example associates the specified route table with the subnet for the specified route table association.

Command::

  aws ec2 replace-route-table-association --association-id rtbassoc-781d0d1a --route-table-id rtb-22574640

Output::

  {
      "NewAssociationId": "rtbassoc-3a1f0f58"
  }

======
Output
======

NewAssociationId -> (string)

  

  The ID of the new association.

  

  



.. _Route Tables: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html
