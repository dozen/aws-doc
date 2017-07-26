[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-keys-and-certificate:


***************************
create-keys-and-certificate
***************************



===========
Description
===========



Creates a 2048 bit RSA key pair and issues an X.509 certificate using the issued public key.

 

**Note** This is the only time AWS IoT issues the private key for this certificate. It is important to keep track of the private key.



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
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

certificateArn -> (string)

  

  The ARN of the certificate.

  

  

certificateId -> (string)

  

  The ID of the certificate. AWS IoT issues a default subject name for the certificate (e.g., AWS IoT Certificate).

  

  

certificatePem -> (string)

  

  The certificate data, in PEM format.

  

  

keyPair -> (structure)

  

  The generated key pair.

  

  PublicKey -> (string)

    

    The public key.

    

    

  PrivateKey -> (string)

    

    The private key.

    

    

  

