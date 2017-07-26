[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-keys-and-certificate:


***************************
create-keys-and-certificate
***************************



===========
Description
===========



Creates a 2048-bit RSA key pair and issues an X.509 certificate using the issued public key.

 

 **Note** This is the only time AWS IoT issues the private key for this certificate, so it is important to keep it in a secure location.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/CreateKeysAndCertificate>`_


========
Synopsis
========

::

    create-keys-and-certificate
  [--set-as-active | --no-set-as-active]
  [--certificate-pem-outfile <value>]
  [--public-key-outfile <value>]
  [--private-key-outfile <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--set-as-active`` | ``--no-set-as-active`` (boolean)


  Specifies whether the certificate is active.

  

``--certificate-pem-outfile`` (string)
Saves the command output contents of certificatePem to the given filename

``--public-key-outfile`` (string)
Saves the command output contents of keyPair.PublicKey to the given filename

``--private-key-outfile`` (string)
Saves the command output contents of keyPair.PrivateKey to the given filename

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

certificateArn -> (string)

  

  The ARN of the certificate.

  

  

certificateId -> (string)

  

  The ID of the certificate. AWS IoT issues a default subject name for the certificate (for example, AWS IoT Certificate).

  

  

certificatePem -> (string)

  

  The certificate data, in PEM format.

  

  

keyPair -> (structure)

  

  The generated key pair.

  

  PublicKey -> (string)

    

    The public key.

    

    

  PrivateKey -> (string)

    

    The private key.

    

    

  

