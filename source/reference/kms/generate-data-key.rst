[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms generate-data-key:


*****************
generate-data-key
*****************



===========
Description
===========



Generates a data key that you can use in your application to locally encrypt data. This call returns a plaintext version of the key in the ``Plaintext`` field of the response object and an encrypted copy of the key in the ``CiphertextBlob`` field. The key is encrypted by using the master key specified by the ``KeyId`` field. To decrypt the encrypted key, pass it to the ``decrypt`` API. 

 

We recommend that you use the following pattern to locally encrypt data: call the ``generate-data-key`` API, use the key returned in the ``Plaintext`` response field to locally encrypt data, and then erase the plaintext data key from memory. Store the encrypted data key (contained in the ``CiphertextBlob`` field) alongside of the locally encrypted data. 

 

.. note::

  You should not call the ``encrypt`` function to re-encrypt your data keys within a region. ``generate-data-key`` always returns the data key encrypted and tied to the customer master key that will be used to decrypt it. There is no need to decrypt it twice. 

 

If you decide to use the optional ``EncryptionContext`` parameter, you must also store the context in full or at least store enough information along with the encrypted data to be able to reconstruct the context when submitting the ciphertext to the ``decrypt`` API. It is a good practice to choose a context that you can reconstruct on the fly to better secure the ciphertext. For more information about how this parameter is used, see `Encryption Context`_ . 

 

To decrypt data, pass the encrypted data key to the ``decrypt`` API. ``decrypt`` uses the associated master key to decrypt the encrypted data key and returns it as plaintext. Use the plaintext data key to locally decrypt your data and then erase the key from memory. You must specify the encryption context, if any, that you specified when you generated the key. The encryption context is logged by CloudTrail, and you can use this log to help track the use of particular data. 



========
Synopsis
========

::

    generate-data-key
  --key-id <value>
  [--encryption-context <value>]
  [--number-of-bytes <value>]
  [--key-spec <value>]
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
   

   

  

``--encryption-context`` (map)


  Name/value pair that contains additional data to be authenticated during the encryption and decryption processes that use the key. This value is logged by AWS CloudTrail to provide context around the data encrypted by the key. 

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--number-of-bytes`` (integer)


  Integer that contains the number of bytes to generate. Common values are 128, 256, 512, and 1024. 1024 is the current limit. We recommend that you use the ``KeySpec`` parameter instead. 

  

``--key-spec`` (string)


  Value that identifies the encryption algorithm and key size to generate a data key for. Currently this can be AES_128 or AES_256. 

  

  Possible values:

  
  *   ``AES_256``

  
  *   ``AES_128``

  

  

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

  

  Ciphertext that contains the encrypted data key. You must store the blob and enough information to reconstruct the encryption context so that the data encrypted by using the key can later be decrypted. You must provide both the ciphertext blob and the encryption context to the  decrypt API to recover the plaintext data key and decrypt the object. 

   

  If you are using the CLI, the value is Base64 encoded. Otherwise, it is not encoded.

  

  

Plaintext -> (blob)

  

  Plaintext that contains the data key. Use this for encryption and decryption and then remove it from memory as soon as possible. 

  

  

KeyId -> (string)

  

  System generated unique identifier of the key to be used to decrypt the encrypted copy of the data key.

  

  



.. _Grant Tokens: http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#grant_token
.. _Encryption Context: http://docs.aws.amazon.com/kms/latest/developerguide/encrypt-context.html
