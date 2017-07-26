[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms get-key-rotation-status:


***********************
get-key-rotation-status
***********************



===========
Description
===========



Retrieves a Boolean value that indicates whether key rotation is enabled for the specified key.



========
Synopsis
========

::

    get-key-rotation-status
  --key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--key-id`` (string)


  A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key. 

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012
   

   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

KeyRotationEnabled -> (boolean)

  

  A Boolean value that specifies whether key rotation is enabled.

  

  

