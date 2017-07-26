[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 confirm-product-instance:


************************
confirm-product-instance
************************



===========
Description
===========



Determines whether a product code is associated with an instance. This action can only be used by the owner of the product code. It is useful when a product code owner needs to verify whether another user's instance is eligible for support.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ConfirmProductInstance>`_


========
Synopsis
========

::

    confirm-product-instance
  --instance-id <value>
  --product-code <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The ID of the instance.

  

``--product-code`` (string)


  The product code. This must be a product code that you own.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To confirm the product instance**

This example determines whether the specified product code is associated with the specified instance.

Command::

  aws ec2 confirm-product-instance --product-code 774F4FF8 --instance-id i-1234567890abcdef0

Output::

  {
    "OwnerId": "123456789012"
  }

======
Output
======

OwnerId -> (string)

  

  The AWS account ID of the instance owner. This is only present if the product code is attached to the instance.

  

  

Return -> (boolean)

  

  The return value of the request. Returns ``true`` if the specified product code is owned by the requester and associated with the specified instance.

  

  

