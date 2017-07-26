[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 confirm-product-instance:


************************
confirm-product-instance
************************



===========
Description
===========



Determines whether a product code is associated with an instance. This action can only be used by the owner of the product code. It is useful when a product code owner needs to verify whether another user's instance is eligible for support.



========
Synopsis
========

::

    confirm-product-instance
  [--dry-run | --no-dry-run]
  --product-code <value>
  --instance-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--product-code`` (string)


  The product code. This must be a product code that you own.

  

``--instance-id`` (string)


  The ID of the instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To confirm the product instance**

This example determines whether the specified product code is associated with the specified instance.

Command::

  aws ec2 confirm-product-instance --product-code 774F4FF8 --instance-id i-5203422c

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

  

  

