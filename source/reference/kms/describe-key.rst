[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms describe-key:


************
describe-key
************



===========
Description
===========



Provides detailed information about the specified customer master key.



========
Synopsis
========

::

    describe-key
  --key-id <value>
  [--grant-tokens <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--key-id`` (string)


  A unique identifier for the customer master key. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/". 

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012
   
  * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012
   
  * Alias Name Example - alias/MyAliasName
   

   

  

``--grant-tokens`` (list)


  A list of grant tokens.

   

  For more information, go to `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

KeyMetadata -> (structure)

  

  Metadata associated with the key.

  

  AWSAccountId -> (string)

    

    The twelve-digit account ID of the AWS account that owns the key.

    

    

  KeyId -> (string)

    

    The globally unique identifier for the key.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) of the key. For examples, see `AWS Key Management Service (AWS KMS)`_ in the Example ARNs section of the *AWS General Reference* .

    

    

  CreationDate -> (timestamp)

    

    The date and time when the key was created.

    

    

  Enabled -> (boolean)

    

    Specifies whether the key is enabled. When ``KeyState`` is ``Enabled`` this value is true, otherwise it is false.

    

    

  Description -> (string)

    

    The friendly description of the key.

    

    

  KeyUsage -> (string)

    

    The cryptographic operations for which you can use the key. Currently the only allowed value is ``ENCRYPT_DECRYPT`` , which means you can use the key for the  encrypt and  decrypt operations.

    

    

  KeyState -> (string)

    

    The state of the customer master key (CMK).

     

    For more information about how key state affects the use of a CMK, go to `How Key State Affects the Use of a Customer Master Key`_ in the *AWS Key Management Service Developer Guide* .

    

    

  DeletionDate -> (timestamp)

    

    The date and time after which AWS KMS deletes the customer master key (CMK). This value is present only when ``KeyState`` is ``PendingDeletion`` , otherwise this value is null.

    

    

  



.. _Grant Tokens: http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#grant_token
.. _How Key State Affects the Use of a Customer Master Key: http://docs.aws.amazon.com/kms/latest/developerguide/key-state.html
.. _AWS Key Management Service (AWS KMS): http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#arn-syntax-kms
