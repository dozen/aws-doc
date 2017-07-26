[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms re-encrypt:


**********
re-encrypt
**********



===========
Description
===========



Encrypts data on the server side with a new customer master key (CMK) without exposing the plaintext of the data on the client side. The data is first decrypted and then reencrypted. You can also use this operation to change the encryption context of a ciphertext.

 

Unlike other operations, ``re-encrypt`` is authorized twice, once as ``ReEncryptFrom`` on the source CMK and once as ``ReEncryptTo`` on the destination CMK. We recommend that you include the ``"kms:ReEncrypt*"`` permission in your `key policies <http://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html>`_ to permit reencryption from or to the CMK. This permission is automatically included in the key policy when you create a CMK through the console, but you must include it manually when you create a CMK programmatically or when you set a key policy with the  put-key-policy operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/ReEncrypt>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ciphertext-blob`` (blob)


  Ciphertext of the data to reencrypt.

  

``--source-encryption-context`` (map)


  Encryption context used to encrypt and decrypt the data specified in the ``CiphertextBlob`` parameter.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--destination-key-id`` (string)


  A unique identifier for the CMK to use to reencrypt the data. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/".

   

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012 
   
  * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName 
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012 
   
  * Alias Name Example - alias/MyAliasName 
   

  

``--destination-encryption-context`` (map)


  Encryption context to use when the data is reencrypted.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



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

CiphertextBlob -> (blob)

  

  The reencrypted data.

  

  

SourceKeyId -> (string)

  

  Unique identifier of the CMK used to originally encrypt the data.

  

  

KeyId -> (string)

  

  Unique identifier of the CMK used to reencrypt the data.

  

  

