[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms decrypt:


*******
decrypt
*******



===========
Description
===========



Decrypts ciphertext. Ciphertext is plaintext that has been previously encrypted by using any of the following functions: 

 
*  generate-data-key 
 
*  generate-data-key-without-plaintext 
 
*  encrypt 
 

 

 

Note that if a caller has been granted access permissions to all keys (through, for example, IAM user policies that grant ``decrypt`` permission on all resources), then ciphertext encrypted by using keys in other accounts where the key grants access to the caller can be decrypted. To remedy this, we recommend that you do not grant ``decrypt`` access in an IAM user policy. Instead grant ``decrypt`` access only in key policies. If you must grant ``decrypt`` access in an IAM user policy, you should scope the resource to specific keys or to specific trusted accounts. 



========
Synopsis
========

::

    decrypt
  --ciphertext-blob <value>
  [--encryption-context <value>]
  [--grant-tokens <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ciphertext-blob`` (blob)


  Ciphertext to be decrypted. The blob includes metadata.

  

``--encryption-context`` (map)


  The encryption context. If this was specified in the  encrypt function, it must be specified here or the decryption operation will fail. For more information, see `Encryption Context`_ . 

  



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

The following command decrypts a KMS encrypted, binary encoded version of a 256 bit key named ``encryptedkey-binary`` in the current folder::

  aws kms decrypt --ciphertext-blob fileb://encryptedkey-binary

The fileb:// prefix instructs the AWS CLI not to attempt to decode the binary data in the file.
  
The output of this command includes the ID of the key used to decrypt the key, and a base64 encoded version of the decrypted key. Use ``base64 -d`` to reverse the base64 encoding and view the original hexadecimal (or otherwise encoded) version of the key. The following command uses an AWS CLI query to isolate the base64 plaintext and pipe it into ``base64``::

  aws kms decrypt --ciphertext-blob fileb://encryptedkey-binary --query Plaintext --output text | base64 -d

======
Output
======

KeyId -> (string)

  

  ARN of the key used to perform the decryption. This value is returned if no errors are encountered during the operation. 

  

  

Plaintext -> (blob)

  

  Decrypted plaintext data. This value may not be returned if the customer master key is not available or if you didn't have permission to use it.

  

  



.. _Grant Tokens: http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#grant_token
.. _Encryption Context: http://docs.aws.amazon.com/kms/latest/developerguide/encrypt-context.html
