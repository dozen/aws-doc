[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms re-encrypt:


**********
re-encrypt
**********



===========
Description
===========



Encrypts data on the server side with a new customer master key without exposing the plaintext of the data on the client side. The data is first decrypted and then encrypted. This operation can also be used to change the encryption context of a ciphertext. 

 

Unlike other actions, ``re-encrypt`` is authorized twice - once as ``ReEncryptFrom`` on the source key and once as ``ReEncryptTo`` on the destination key. We therefore recommend that you include the ``"action":"kms:ReEncrypt*"`` statement in your key policies to permit re-encryption from or to the key. The statement is included automatically when you authorize use of the key through the console but must be included manually when you set a policy by using the  put-key-policy function. 



========
Synopsis
========

::

    re-encrypt
  --ciphertext-blob <value>
  [--source-encryption-context <value>]
  --destination-key-id <value>
  [--destination-encryption-context <value>]
  [--grant-tokens <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ciphertext-blob`` (blob)


  Ciphertext of the data to re-encrypt.

  

``--source-encryption-context`` (map)


  Encryption context used to encrypt and decrypt the data specified in the ``CiphertextBlob`` parameter. 

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--destination-key-id`` (string)


  A unique identifier for the customer master key used to re-encrypt the data. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/". 

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012
   
  * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012
   
  * Alias Name Example - alias/MyAliasName
   

   

  

``--destination-encryption-context`` (map)


  Encryption context to be used when the data is re-encrypted.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



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

CiphertextBlob -> (blob)

  

  The re-encrypted data. If you are using the CLI, the value is Base64 encoded. Otherwise, it is not encoded.

  

  

SourceKeyId -> (string)

  

  Unique identifier of the key used to originally encrypt the data.

  

  

KeyId -> (string)

  

  Unique identifier of the key used to re-encrypt the data.

  

  



.. _Grant Tokens: http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#grant_token
