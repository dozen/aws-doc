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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/Encrypt>`_


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
   

  

``--plaintext`` (blob)


  Data to be encrypted.

  

``--encryption-context`` (map)


  Name-value pair that specifies the encryption context to be used for authenticated encryption. If used here, the same value must be supplied to the ``decrypt`` API or decryption will fail. For more information, see `Encryption Context <http://docs.aws.amazon.com/kms/latest/developerguide/encryption-context.html>`_ .

  



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



========
Examples
========

The following command demonstrates the recommended way to encrypt data with the AWS CLI.

.. code::

    aws kms encrypt --key-id 1234abcd-12ab-34cd-56ef-1234567890ab --plaintext fileb://ExamplePlaintextFile --output text --query CiphertextBlob | base64 --decode > ExampleEncryptedFile

The command does several things:

#. Uses the ``fileb://`` prefix to specify the ``--plaintext`` parameter.

    The ``fileb://`` prefix instructs the CLI to read the data to encrypt, called the *plaintext*, from a file and pass the file's contents to the command's ``--plaintext`` parameter. If the file is not in the current directory, type the full path to file. For example: ``fileb:///var/tmp/ExamplePlaintextFile`` or ``fileb://C:\Temp\ExamplePlaintextFile``.

    For more information about reading AWS CLI parameter values from a file, see `Loading Parameters from a File <https://docs.aws.amazon.com/cli/latest/userguide/cli-using-param.html#cli-using-param-file>`_ in the *AWS Command Line Interface User Guide* and `Best Practices for Local File Parameters <https://blogs.aws.amazon.com/cli/post/TxLWWN1O25V1HE/Best-Practices-for-Local-File-Parameters>`_ on the AWS Command Line Tool Blog.

#. Uses the ``--output`` and ``--query`` parameters to control the command's output.

    These parameters extract the encrypted data, called the *ciphertext*, from the command's output.

    For more information about controlling output, see `Controlling Command Output <https://docs.aws.amazon.com/cli/latest/userguide/controlling-output.html>`_ in the *AWS Command Line Interface User Guide*.

#. Uses the ``base64`` utility to decode the extracted output.

    This utility decodes the extracted ciphertext to binary data. The ciphertext that is returned by a successful ``encrypt`` command is base64-encoded text. You must decode this text before you can use the AWS CLI to decrypt it.

#. Saves the binary ciphertext to a file.

    The final part of the command (``> ExampleEncryptedFile``) saves the binary ciphertext to a file to make decryption easier. For an example command that uses the AWS CLI to decrypt data, see the `decrypt examples <decrypt.html#examples>`_.

**Example: Using the AWS CLI to encrypt data from the Windows command prompt**

The preceding example assumes the ``base64`` utility is available, which is commonly the case on Linux and Mac OS X. For the Windows command prompt, use ``certutil`` instead of ``base64``. This requires two commands, as shown in the following examples.

.. code::

    aws kms encrypt --key-id 1234abcd-12ab-34cd-56ef-1234567890ab --plaintext fileb://ExamplePlaintextFile --output text --query CiphertextBlob > C:\Temp\ExampleEncryptedFile.base64

.. code::

    certutil -decode C:\Temp\ExampleEncryptedFile.base64 C:\Temp\ExampleEncryptedFile

======
Output
======

CiphertextBlob -> (blob)

  

  The encrypted plaintext. If you are using the CLI, the value is Base64 encoded. Otherwise, it is not encoded.

  

  

KeyId -> (string)

  

  The ID of the key used during encryption.

  

  

