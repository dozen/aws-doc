[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms revoke-grant:


************
revoke-grant
************



===========
Description
===========



Revokes a grant. You can revoke a grant to actively deny operations that depend on it.



========
Synopsis
========

::

    revoke-grant
  --key-id <value>
  --grant-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--key-id`` (string)


  A unique identifier for the customer master key associated with the grant. This value can be a globally unique identifier or the fully specified ARN to a key. 

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012
   

   

  

``--grant-id`` (string)


  Identifier of the grant to be revoked.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None