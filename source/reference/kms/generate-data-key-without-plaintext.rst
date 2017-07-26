[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms generate-data-key-without-plaintext:


***********************************
generate-data-key-without-plaintext
***********************************



===========
Description
===========



Returns a data encryption key encrypted under a customer master key (CMK). This operation is identical to  generate-data-key but returns only the encrypted copy of the data key.

 

This operation is useful in a system that has multiple components with different degrees of trust. For example, consider a system that stores encrypted data in containers. Each container stores the encrypted data and an encrypted copy of the data key. One component of the system, called the *control plane* , creates new containers. When it creates a new container, it uses this operation (``generate-data-key-without-plaintext`` ) to get an encrypted data key and then stores it in the container. Later, a different component of the system, called the *data plane* , puts encrypted data into the containers. To do this, it passes the encrypted data key to the  decrypt operation, then uses the returned plaintext data key to encrypt data, and finally stores the encrypted data in the container. In this system, the control plane never sees the plaintext data key.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/GenerateDataKeyWithoutPlaintext>`_


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



``--key-spec`` (string)


  The length of the data encryption key. Use ``AES_128`` to generate a 128-bit symmetric key, or ``AES_256`` to generate a 256-bit symmetric key.

  

  Possible values:

  
  *   ``AES_256``

  
  *   ``AES_128``

  

  

``--number-of-bytes`` (integer)


  The length of the data encryption key in bytes. For example, use the value 64 to generate a 512-bit data key (64 bytes is 512 bits). For common key lengths (128-bit and 256-bit symmetric keys), we recommend that you use the ``KeySpec`` field instead of this one.

  

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

  

  

KeyId -> (string)

  

  The identifier of the CMK under which the data encryption key was generated and encrypted.

  

  

