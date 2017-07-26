[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms generate-data-key-without-plaintext:


***********************************
generate-data-key-without-plaintext
***********************************



===========
Description
===========



Returns a data key encrypted by a customer master key without the plaintext copy of that key. Otherwise, this API functions exactly like  generate-data-key . You can use this API to, for example, satisfy an audit requirement that an encrypted key be made available without exposing the plaintext copy of that key. 



========
Synopsis
========

::

    generate-data-key-without-plaintext
  --key-id <value>
  [--encryption-context <value>]
  [--key-spec <value>]
  [--number-of-bytes <value>]
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


  Name:value pair that contains additional data to be authenticated during the encryption and decryption processes. 

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--key-spec`` (string)


  Value that identifies the encryption algorithm and key size. Currently this can be AES_128 or AES_256. 

  

  Possible values:

  
  *   ``AES_256``

  
  *   ``AES_128``

  

  

``--number-of-bytes`` (integer)


  Integer that contains the number of bytes to generate. Common values are 128, 256, 512, 1024 and so on. We recommend that you use the ``KeySpec`` parameter instead. 

  

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

  

  Ciphertext that contains the wrapped data key. You must store the blob and encryption context so that the key can be used in a future decrypt operation. 

   

  If you are using the CLI, the value is Base64 encoded. Otherwise, it is not encoded. 

  

  

KeyId -> (string)

  

  System generated unique identifier of the key to be used to decrypt the encrypted copy of the data key.

  

  



.. _Grant Tokens: http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#grant_token
