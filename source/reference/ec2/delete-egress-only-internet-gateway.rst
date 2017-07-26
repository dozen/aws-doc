[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-egress-only-internet-gateway:


***********************************
delete-egress-only-internet-gateway
***********************************



===========
Description
===========



Deletes an egress-only Internet gateway.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DeleteEgressOnlyInternetGateway>`_


========
Synopsis
========

::

    delete-egress-only-internet-gateway
  [--dry-run | --no-dry-run]
  --egress-only-internet-gateway-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--egress-only-internet-gateway-id`` (string)


  The ID of the egress-only Internet gateway.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an egress-only Internet gateway**

This example deletes the specified egress-only Internet gateway.

Command::

  aws ec2 delete-egress-only-internet-gateway --egress-only-internet-gateway-id eigw-01eadbd45ecd7943f

Output::

  {
    "ReturnCode": true
  }

======
Output
======

ReturnCode -> (boolean)

  

  Returns ``true`` if the request succeeds; otherwise, it returns an error.

  

  

