[ :ref:`aws <cli:aws>` . :ref:`acm <cli:aws acm>` ]

.. _cli:aws acm import-certificate:


******************
import-certificate
******************



===========
Description
===========



Imports an SSL/TLS certificate into AWS Certificate Manager (ACM) to use with `ACM's integrated AWS services <http://docs.aws.amazon.com/acm/latest/userguide/acm-services.html>`_ .

 

.. note::

   

  ACM does not provide `managed renewal <http://docs.aws.amazon.com/acm/latest/userguide/acm-renewal.html>`_ for certificates that you import.

   

 

For more information about importing certificates into ACM, including the differences between certificates that you import and those that ACM provides, see `Importing Certificates <http://docs.aws.amazon.com/acm/latest/userguide/import-certificate.html>`_ in the *AWS Certificate Manager User Guide* .

 

To import a certificate, you must provide the certificate and the matching private key. When the certificate is not self-signed, you must also provide a certificate chain. You can omit the certificate chain when importing a self-signed certificate.

 

The certificate, private key, and certificate chain must be PEM-encoded. For more information about converting these items to PEM format, see `Importing Certificates Troubleshooting <http://docs.aws.amazon.com/acm/latest/userguide/import-certificate.html#import-certificate-troubleshooting>`_ in the *AWS Certificate Manager User Guide* .

 

To import a new certificate, omit the ``CertificateArn`` field. Include this field only when you want to replace a previously imported certificate.

 

This operation returns the `Amazon Resource Name (ARN) <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ of the imported certificate.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/acm-2015-12-08/ImportCertificate>`_


========
Synopsis
========

::

    import-certificate
  [--certificate-arn <value>]
  --certificate <value>
  --private-key <value>
  [--certificate-chain <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-arn`` (string)


  The `Amazon Resource Name (ARN) <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ of an imported certificate to replace. To import a new certificate, omit this field.

  

``--certificate`` (blob)


  The certificate to import. It must meet the following requirements:

   

   
  * Must be PEM-encoded. 
   
  * Must contain a 1024-bit or 2048-bit RSA public key. 
   
  * Must be valid at the time of import. You cannot import a certificate before its validity period begins (the certificate's ``NotBefore`` date) or after it expires (the certificate's ``NotAfter`` date). 
   

  

``--private-key`` (blob)


  The private key that matches the public key in the certificate. It must meet the following requirements:

   

   
  * Must be PEM-encoded. 
   
  * Must be unencrypted. You cannot import a private key that is protected by a password or passphrase. 
   

  

``--certificate-chain`` (blob)


  The certificate chain. It must be PEM-encoded.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CertificateArn -> (string)

  

  The `Amazon Resource Name (ARN) <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ of the imported certificate.

  

  

