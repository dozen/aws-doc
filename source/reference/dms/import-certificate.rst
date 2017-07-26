[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms import-certificate:


******************
import-certificate
******************



===========
Description
===========



Uploads the specified certificate.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/ImportCertificate>`_


========
Synopsis
========

::

    import-certificate
  --certificate-identifier <value>
  [--certificate-pem <value>]
  [--certificate-wallet <value>]
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-identifier`` (string)


  The customer-assigned name of the certificate. Valid characters are A-z and 0-9.

  

``--certificate-pem`` (string)


  The contents of the .pem X.509 certificate file for the certificate.

  

``--certificate-wallet`` (blob)


  The location of the imported Oracle Wallet certificate for use with SSL.

  

``--tags`` (list)


  The tags associated with the certificate.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Certificate -> (structure)

  

  The certificate to be uploaded.

  

  CertificateIdentifier -> (string)

    

    The customer-assigned name of the certificate. Valid characters are A-z and 0-9.

    

    

  CertificateCreationDate -> (timestamp)

    

    The date that the certificate was created.

    

    

  CertificatePem -> (string)

    

    The contents of the .pem X.509 certificate file for the certificate.

    

    

  CertificateWallet -> (blob)

    

    The location of the imported Oracle Wallet certificate for use with SSL.

    

    

  CertificateArn -> (string)

    

    The Amazon Resource Name (ARN) for the certificate.

    

    

  CertificateOwner -> (string)

    

    The owner of the certificate.

    

    

  ValidFromDate -> (timestamp)

    

    The beginning date that the certificate is valid.

    

    

  ValidToDate -> (timestamp)

    

    The final date that the certificate is valid.

    

    

  SigningAlgorithm -> (string)

    

    The signing algorithm for the certificate.

    

    

  KeyLength -> (integer)

    

    The key length of the cryptographic algorithm being used.

    

    

  

