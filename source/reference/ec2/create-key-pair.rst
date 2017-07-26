[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-key-pair:


***************
create-key-pair
***************



===========
Description
===========



Creates a 2048-bit RSA key pair with the specified name. Amazon EC2 stores the public key and displays the private key for you to save to a file. The private key is returned as an unencrypted PEM encoded PKCS#8 private key. If a key with the specified name already exists, Amazon EC2 returns an error.

 

You can have up to five thousand key pairs per region.

 

The key pair returned to you is available only in the region in which you create it. To create a key pair that is available in all regions, use  import-key-pair .

 

For more information about key pairs, see `Key Pairs <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateKeyPair>`_


========
Synopsis
========

::

    create-key-pair
  --key-name <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-name`` (string)


  A unique name for the key pair.

   

  Constraints: Up to 255 ASCII characters

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a key pair**

This example creates a key pair named ``MyKeyPair``.

Command::

  aws ec2 create-key-pair --key-name MyKeyPair

The output is an ASCII version of the private key and key fingerprint. You need to save the key to a file.

For more information, see `Using Key Pairs`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Key Pairs`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-keypairs.html



======
Output
======

KeyFingerprint -> (string)

  

  The SHA-1 digest of the DER encoded private key.

  

  

KeyMaterial -> (string)

  

  An unencrypted PEM encoded RSA private key.

  

  

KeyName -> (string)

  

  The name of the key pair.

  

  

