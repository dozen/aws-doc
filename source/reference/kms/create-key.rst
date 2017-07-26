[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms create-key:


**********
create-key
**********



===========
Description
===========



Creates a customer master key. Customer master keys can be used to encrypt small amounts of data (less than 4K) directly, but they are most commonly used to encrypt or envelope data keys that are then used to encrypt customer data. For more information about data keys, see  generate-data-key and  generate-data-key-without-plaintext .



========
Synopsis
========

::

    create-key
  [--policy <value>]
  [--description <value>]
  [--key-usage <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy`` (string)


  Policy to attach to the key. This is required and delegates back to the account. The key is the root of trust. The policy size limit is 32 KiB (32768 bytes). 

  

``--description`` (string)


  Description of the key. We recommend that you choose a description that helps your customer decide whether the key is appropriate for a task. 

  

``--key-usage`` (string)


  Specifies the intended use of the key. Currently this defaults to ENCRYPT/DECRYPT, and only symmetric encryption and decryption are supported. 

  

  Possible values:

  
  *   ``ENCRYPT_DECRYPT``

  

  

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

    

    

  



.. _How Key State Affects the Use of a Customer Master Key: http://docs.aws.amazon.com/kms/latest/developerguide/key-state.html
.. _AWS Key Management Service (AWS KMS): http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#arn-syntax-kms
