[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-server-certificate:


**********************
get-server-certificate
**********************



===========
Description
===========



Retrieves information about the specified server certificate stored in IAM.

 

For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetServerCertificate>`_


========
Synopsis
========

::

    get-server-certificate
  --server-certificate-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--server-certificate-name`` (string)


  The name of the server certificate you want to retrieve information about.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ServerCertificate -> (structure)

  

  A structure containing details about the server certificate.

  

  ServerCertificateMetadata -> (structure)

    

    The meta information of the server certificate, such as its name, path, ID, and ARN.

    

    Path -> (string)

      

      The path to the server certificate. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

      

      

    ServerCertificateName -> (string)

      

      The name that identifies the server certificate.

      

      

    ServerCertificateId -> (string)

      

      The stable and unique string identifying the server certificate. For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) specifying the server certificate. For more information about ARNs and how to use them in policies, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

      

      

    UploadDate -> (timestamp)

      

      The date when the server certificate was uploaded.

      

      

    Expiration -> (timestamp)

      

      The date on which the certificate is set to expire.

      

      

    

  CertificateBody -> (string)

    

    The contents of the public key certificate.

    

    

  CertificateChain -> (string)

    

    The contents of the public key certificate chain.

    

    

  

