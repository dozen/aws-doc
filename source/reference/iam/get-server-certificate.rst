[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-server-certificate:


**********************
get-server-certificate
**********************



===========
Description
===========



Retrieves information about the specified server certificate.

 

For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .



========
Synopsis
========

::

    get-server-certificate
  --server-certificate-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--server-certificate-name`` (string)


  The name of the server certificate you want to retrieve information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ServerCertificate -> (structure)

  

  Information about the server certificate.

  

  ServerCertificateMetadata -> (structure)

    

    The meta information of the server certificate, such as its name, path, ID, and ARN.

    

    Path -> (string)

      

      The path to the server certificate. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    ServerCertificateName -> (string)

      

      The name that identifies the server certificate.

      

      

    ServerCertificateId -> (string)

      

      The stable and unique string identifying the server certificate. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) specifying the server certificate. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    UploadDate -> (timestamp)

      

      The date when the server certificate was uploaded.

      

      

    Expiration -> (timestamp)

      

      The date on which the certificate is set to expire.

      

      

    

  CertificateBody -> (string)

    

    The contents of the public key certificate.

    

    

  CertificateChain -> (string)

    

    The contents of the public key certificate chain.

    

    

  



.. _Working with Server Certificates: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
