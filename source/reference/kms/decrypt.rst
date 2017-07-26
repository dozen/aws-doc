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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/Decrypt>`_


========
Synopsis
========

::

    decrypt
  --ciphertext-blob <value>
  [--encryption-context <value>]
  [--grant-tokens <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ciphertext-blob`` (blob)


  Ciphertext to be decrypted. The blob includes metadata.

  

``--encryption-context`` (map)


  The encryption context. If this was specified in the  encrypt function, it must be specified here or the decryption operation will fail. For more information, see `Encryption Context <http://docs.aws.amazon.com/kms/latest/developerguide/encryption-context.html>`_ .

  



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

The following command demonstrates the recommended way to decrypt data with the AWS CLI.

.. code::

    aws kms decrypt --ciphertext-blob fileb://ExampleEncryptedFile --output text --query Plaintext | base64 --decode > ExamplePlaintextFile

The command does several things:

#. Uses the ``fileb://`` prefix to specify the ``--ciphertext-blob`` parameter.

    The ``fileb://`` prefix instructs the CLI to read the encrypted data, called the *ciphertext*, from a file and pass the file's contents to the command's ``--ciphertext-blob`` parameter.  If the file is not in the current directory, type the full path to file. For example: ``fileb:///var/tmp/ExampleEncryptedFile`` or ``fileb://C:\Temp\ExampleEncryptedFile``.

    For more information about reading AWS CLI parameter values from a file, see `Loading Parameters from a File <https://docs.aws.amazon.com/cli/latest/userguide/cli-using-param.html#cli-using-param-file>`_ in the *AWS Command Line Interface User Guide* and `Best Practices for Local File Parameters <https://blogs.aws.amazon.com/cli/post/TxLWWN1O25V1HE/Best-Practices-for-Local-File-Parameters>`_ on the AWS Command Line Tool Blog.

    The command assumes the ciphertext in ``ExampleEncryptedFile`` is binary data. The `encrypt examples <encrypt.html#examples>`_ demonstrate how to save a ciphertext this way.

#. Uses the ``--output`` and ``--query`` parameters to control the command's output.

    These parameters extract the decrypted data, called the *plaintext*, from the command's output. For more information about controlling output, see `Controlling Command Output <https://docs.aws.amazon.com/cli/latest/userguide/controlling-output.html>`_ in the *AWS Command Line Interface User Guide*.

#. Uses the ``base64`` utility.

    This utility decodes the extracted plaintext to binary data. The plaintext that is returned by a successful ``decrypt`` command is base64-encoded text. You must decode this text to obtain the original plaintext.

#. Saves the binary plaintext to a file.

    The final part of the command (``> ExamplePlaintextFile``) saves the binary plaintext data to a file.

**Example: Using the AWS CLI to decrypt data from the Windows command prompt**

The preceding example assumes the ``base64`` utility is available, which is commonly the case on Linux and Mac OS X. For the Windows command prompt, use ``certutil`` instead of ``base64``. This requires two commands, as shown in the following examples.

.. code::

    aws kms decrypt --ciphertext-blob fileb://ExampleEncryptedFile --output text --query Plaintext > ExamplePlaintextFile.base64

.. code::

    certutil -decode ExamplePlaintextFile.base64 ExamplePlaintextFile

======
Output
======

KeyId -> (string)

  

  ARN of the key used to perform the decryption. This value is returned if no errors are encountered during the operation.

  

  

Plaintext -> (blob)

  

  Decrypted plaintext data. This value may not be returned if the customer master key is not available or if you didn't have permission to use it.

  

  

