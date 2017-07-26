[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 import-key-pair:


***************
import-key-pair
***************



===========
Description
===========



Imports the public key from an RSA key pair that you created with a third-party tool. Compare this with  create-key-pair , in which AWS creates the key pair and gives the keys to you (AWS keeps a copy of the public key). With ImportKeyPair, you create the key pair and give AWS just the public key. The private key is never transferred between you and AWS.

 

For more information about key pairs, see `Key Pairs <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ImportKeyPair>`_


========
Synopsis
========

::

    import-key-pair
  [--dry-run | --no-dry-run]
  --key-name <value>
  --public-key-material <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--key-name`` (string)


  A unique name for the key pair.

  

``--public-key-material`` (blob)


  The public key. For API calls, the text must be base64-encoded. For command line tools, base64 encoding is performed for you.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To import a public key**

First, generate a key pair with the tool of your choice. For example, use this OpenSSL command:

Command::

  openssl genrsa -out my-key.pem 2048
  
Next, save the public key to a local file. For example, use this OpenSSL command:

Command::

  openssl rsa -in my-key.pem -pubout > my-key.pub
  
Finally, this example command imports the specified public key. The public key is the text in the .pub file that is between ``-----BEGIN PUBLIC KEY-----`` and ``-----END PUBLIC KEY-----``.

Command::

  aws ec2 import-key-pair --key-name my-key --public-key-material MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAuhrGNglwb2Zz/Qcz1zV+l12fJOnWmJxC2GMwQOjAX/L7p01o9vcLRoHXxOtcHBx0TmwMo+i85HWMUE7aJtYclVWPMOeepFmDqR1AxFhaIc9jDe88iLA07VK96wY4oNpp8+lICtgCFkuXyunsk4+KhuasN6kOpk7B2w5cUWveooVrhmJprR90FOHQB2Uhe9MkRkFjnbsA/hvZ/Ay0Cflc2CRZm/NG00lbLrV4l/SQnZmP63DJx194T6pI3vAev2+6UMWSwptNmtRZPMNADjmo50KiG2c3uiUIltiQtqdbSBMh9ztL/98AHtn88JG0s8u2uSRTNEHjG55tyuMbLD40QEXAMPLE
  
Output::

  {
    "KeyName": "my-key",
    "KeyFingerprint": "1f:51:ae:28:bf:89:e9:d8:1f:25:5d:37:2d:7d:b8:ca"
  }

======
Output
======

KeyFingerprint -> (string)

  

  The MD5 public key fingerprint as specified in section 4 of RFC 4716.

  

  

KeyName -> (string)

  

  The key pair name you provided.

  

  

