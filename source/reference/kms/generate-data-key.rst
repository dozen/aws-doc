[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms generate-data-key:


*****************
generate-data-key
*****************



===========
Description
===========



Returns a data encryption key that you can use in your application to encrypt data locally.

 

You must specify the customer master key (CMK) under which to generate the data key. You must also specify the length of the data key using either the ``KeySpec`` or ``NumberOfBytes`` field. You must specify one field or the other, but not both. For common key lengths (128-bit and 256-bit symmetric keys), we recommend that you use ``KeySpec`` .

 

This operation returns a plaintext copy of the data key in the ``Plaintext`` field of the response, and an encrypted copy of the data key in the ``CiphertextBlob`` field. The data key is encrypted under the CMK specified in the ``KeyId`` field of the request.

 

We recommend that you use the following pattern to encrypt data locally in your application:

 

 
* Use this operation (``generate-data-key`` ) to retrieve a data encryption key. 
 
* Use the plaintext data encryption key (returned in the ``Plaintext`` field of the response) to encrypt data locally, then erase the plaintext data key from memory. 
 
* Store the encrypted data key (returned in the ``CiphertextBlob`` field of the response) alongside the locally encrypted data. 
 

 

To decrypt data locally:

 

 
* Use the  decrypt operation to decrypt the encrypted data key into a plaintext copy of the data key. 
 
* Use the plaintext data key to decrypt data locally, then erase the plaintext data key from memory. 
 

 

To return only an encrypted copy of the data key, use  generate-data-key-without-plaintext . To return a random byte string that is cryptographically secure, use  generate-random .

 

If you use the optional ``EncryptionContext`` field, you must store at least enough information to be able to reconstruct the full encryption context when you later send the ciphertext to the  decrypt operation. It is a good practice to choose an encryption context that you can reconstruct on the fly to better secure the ciphertext. For more information, see `Encryption Context <http://docs.aws.amazon.com/kms/latest/developerguide/encryption-context.html>`_ in the *AWS Key Management Service Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/GenerateDataKey>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-id`` (string)


  The identifier of the CMK under which to generate and encrypt the data encryption key.

   

  A valid identifier is the unique key ID or the Amazon Resource Name (ARN) of the CMK, or the alias name or ARN of an alias that refers to the CMK. Examples:

   

   
  * Unique key ID: ``1234abcd-12ab-34cd-56ef-1234567890ab``   
   
  * CMK ARN: ``arn:aws:kms:us-east-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab``   
   
  * Alias name: ``alias/ExampleAlias``   
   
  * Alias ARN: ``arn:aws:kms:us-east-2:111122223333:alias/ExampleAlias``   
   

  

``--encryption-context`` (map)


  A set of key-value pairs that represents additional authenticated data.

   

  For more information, see `Encryption Context <http://docs.aws.amazon.com/kms/latest/developerguide/encryption-context.html>`_ in the *AWS Key Management Service Developer Guide* .

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--number-of-bytes`` (integer)


  The length of the data encryption key in bytes. For example, use the value 64 to generate a 512-bit data key (64 bytes is 512 bits). For common key lengths (128-bit and 256-bit symmetric keys), we recommend that you use the ``KeySpec`` field instead of this one.

  

``--key-spec`` (string)


  The length of the data encryption key. Use ``AES_128`` to generate a 128-bit symmetric key, or ``AES_256`` to generate a 256-bit symmetric key.

  

  Possible values:

  
  *   ``AES_256``

  
  *   ``AES_128``

  

  

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

  

  The encrypted data encryption key.

  

  

Plaintext -> (blob)

  

  The data encryption key. Use this data key for local encryption and decryption, then remove it from memory as soon as possible.

  

  

KeyId -> (string)

  

  The identifier of the CMK under which the data encryption key was generated and encrypted.

  

  

