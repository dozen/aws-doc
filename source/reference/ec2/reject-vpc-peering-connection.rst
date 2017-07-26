[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 reject-vpc-peering-connection:


*****************************
reject-vpc-peering-connection
*****************************



===========
Description
===========



Rejects a VPC peering connection request. The VPC peering connection must be in the ``pending-acceptance`` state. Use the  describe-vpc-peering-connections request to view your outstanding VPC peering connection requests. To delete an active VPC peering connection, or to delete a VPC peering connection request that you initiated, use  delete-vpc-peering-connection .



========
Synopsis
========

::

    reject-vpc-peering-connection
  [--dry-run | --no-dry-run]
  --vpc-peering-connection-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-peering-connection-id`` (string)


  The ID of the VPC peering connection.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To reject a VPC peering connection**

This example rejects the specified VPC peering connection request.

Command::

  aws ec2 reject-vpc-peering-connection --vpc-peering-connection-id pcx-1a2b3c4d

Output::

  {
      "Return": true
  }

======
Output
======

Return -> (boolean)

  

  Returns ``true`` if the request succeeds; otherwise, it returns an error.

  

  

