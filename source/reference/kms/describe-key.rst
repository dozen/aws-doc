[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms describe-key:


************
describe-key
************



===========
Description
===========



Provides detailed information about the specified customer master key.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/DescribeKey>`_


========
Synopsis
========

::

    describe-key
  --key-id <value>
  [--grant-tokens <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

   

  For more information, see `Grant Tokens <http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#grant_token>`_ in the *AWS Key Management Service Developer Guide* .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

KeyMetadata -> (structure)

  

  Metadata associated with the key.

  

  AWSAccountId -> (string)

    

    The twelve-digit account ID of the AWS account that owns the CMK.

    

    

  KeyId -> (string)

    

    The globally unique identifier for the CMK.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) of the CMK. For examples, see `AWS Key Management Service (AWS KMS) <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#arn-syntax-kms>`_ in the Example ARNs section of the *AWS General Reference* .

    

    

  CreationDate -> (timestamp)

    

    The date and time when the CMK was created.

    

    

  Enabled -> (boolean)

    

    Specifies whether the CMK is enabled. When ``KeyState`` is ``Enabled`` this value is true, otherwise it is false.

    

    

  Description -> (string)

    

    The description of the CMK.

    

    

  KeyUsage -> (string)

    

    The cryptographic operations for which you can use the CMK. Currently the only allowed value is ``ENCRYPT_DECRYPT`` , which means you can use the CMK for the  encrypt and  decrypt operations.

    

    

  KeyState -> (string)

    

    The state of the CMK.

     

    For more information about how key state affects the use of a CMK, see `How Key State Affects the Use of a Customer Master Key <http://docs.aws.amazon.com/kms/latest/developerguide/key-state.html>`_ in the *AWS Key Management Service Developer Guide* .

    

    

  DeletionDate -> (timestamp)

    

    The date and time after which AWS KMS deletes the CMK. This value is present only when ``KeyState`` is ``PendingDeletion`` , otherwise this value is omitted.

    

    

  ValidTo -> (timestamp)

    

    The time at which the imported key material expires. When the key material expires, AWS KMS deletes the key material and the CMK becomes unusable. This value is present only for CMKs whose ``Origin`` is ``EXTERNAL`` and whose ``ExpirationModel`` is ``KEY_MATERIAL_EXPIRES`` , otherwise this value is omitted.

    

    

  Origin -> (string)

    

    The source of the CMK's key material. When this value is ``AWS_KMS`` , AWS KMS created the key material. When this value is ``EXTERNAL`` , the key material was imported from your existing key management infrastructure or the CMK lacks key material.

    

    

  ExpirationModel -> (string)

    

    Specifies whether the CMK's key material expires. This value is present only when ``Origin`` is ``EXTERNAL`` , otherwise this value is omitted.

    

    

  KeyManager -> (string)

    

    The CMK's manager. CMKs are either customer-managed or AWS-managed. For more information about the difference, see `Customer Master Keys <http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#master_keys>`_ in the *AWS Key Management Service Developer Guide* .

    

    

  

