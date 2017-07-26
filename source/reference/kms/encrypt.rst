[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms encrypt:


*******
encrypt
*******



===========
Description
===========



Encrypts plaintext into ciphertext by using a customer master key. The ``encrypt`` function has two primary use cases: 

 
* You can encrypt up to 4 KB of arbitrary data such as an RSA key, a database password, or other sensitive customer information.
 
* If you are moving encrypted data from one region to another, you can use this API to encrypt in the new region the plaintext data key that was used to encrypt the data in the original region. This provides you with an encrypted copy of the data key that can be decrypted in the new region and used there to decrypt the encrypted data. 
 

 

 

Unless you are moving encrypted data from one region to another, you don't use this function to encrypt a generated data key within a region. You retrieve data keys already encrypted by calling the  generate-data-key or  generate-data-key-without-plaintext function. Data keys don't need to be encrypted again by calling ``encrypt`` . 

 

If you want to encrypt data locally in your application, you can use the ``generate-data-key`` function to return a plaintext data encryption key and a copy of the key encrypted under the customer master key (CMK) of your choosing. 



========
Synopsis
========

::

    encrypt
  --key-id <value>
  --plaintext <value>
  [--encryption-context <value>]
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
   

   

  

``--plaintext`` (blob)


  Data to be encrypted.

  

``--encryption-context`` (map)


  Name/value pair that specifies the encryption context to be used for authenticated encryption. If used here, the same value must be supplied to the ``decrypt`` API or decryption will fail. For more information, see `Encryption Context`_ . 

  



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



========
Examples
========

This example shows how to encrypt the string ``"1\!2@3#4$5%6^7&8*9(0)-_=+"``
and save the binary contents to a file::

  aws kms encrypt --key-id my-key-id --plaintext "1\!2@3#4$5%6^7&8*9(0)-_=+" --query CiphertextBlob --output text | base64 --decode > /tmp/encrypted


If you want to decrypt the contents of the file above you can use this
command::

  echo "Decrypted is: $(aws kms decrypt --ciphertext-blob fileb:///tmp/encrypted  --output text --query Plaintext | base64 --decode)"

Note the use of the ``fileb://`` prefix in the ``decrypt`` command above.  This
indicates that the referenced file contains binary contents, and that the file
contents are not decoded before being used.


======
Output
======

CiphertextBlob -> (blob)

  

  The encrypted plaintext. If you are using the CLI, the value is Base64 encoded. Otherwise, it is not encoded.

  

  

KeyId -> (string)

  

  The ID of the key used during encryption.

  

  



.. _Grant Tokens: http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#grant_token
.. _Encryption Context: http://docs.aws.amazon.com/kms/latest/developerguide/encrypt-context.html
