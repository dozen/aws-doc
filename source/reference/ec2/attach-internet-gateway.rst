[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 attach-internet-gateway:


***********************
attach-internet-gateway
***********************



===========
Description
===========



Attaches an Internet gateway to a VPC, enabling connectivity between the Internet and the VPC. For more information about your VPC and Internet gateway, see the `Amazon Virtual Private Cloud User Guide <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AttachInternetGateway>`_


========
Synopsis
========

::

    attach-internet-gateway
  [--dry-run | --no-dry-run]
  --internet-gateway-id <value>
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--internet-gateway-id`` (string)


  The ID of the Internet gateway.

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attach an Internet gateway to your VPC**

This example attaches the specified Internet gateway to the specified VPC. If the command succeeds, no output is returned.

Command::

  aws ec2 attach-internet-gateway --internet-gateway-id igw-c0a643a9 --vpc-id vpc-a01106c2

======
Output
======

None