[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms get-key-rotation-status:


***********************
get-key-rotation-status
***********************



===========
Description
===========



Retrieves a Boolean value that indicates whether key rotation is enabled for the specified key.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/GetKeyRotationStatus>`_


========
Synopsis
========

::

    get-key-rotation-status
  --key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-id`` (string)


  A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key.

   

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

KeyRotationEnabled -> (boolean)

  

  A Boolean value that specifies whether key rotation is enabled.

  

  

