[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam upload-server-certificate:


*************************
upload-server-certificate
*************************



===========
Description
===========



Uploads a server certificate entity for the AWS account. The server certificate entity includes a public key certificate, a private key, and an optional certificate chain, which should all be PEM-encoded. 

 

For more information about working with server certificates, including a list of AWS services that can use the server certificates that you manage with IAM, go to `Working with Server Certificates`_ in the *IAM User Guide* .

 

For information about the number of server certificates you can upload, see `Limitations on IAM Entities and Objects`_ in the *IAM User Guide* . 

 

.. note::

  Because the body of the public key certificate, private key, and the certificate chain can be large, you should use POST rather than GET when calling ``upload-server-certificate`` . For information about setting up signatures and authorization through the API, go to `Signing AWS API Requests`_ in the *AWS General Reference* . For general information about using the Query API with IAM, go to `Calling the API by Making HTTP Query Requests`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    upload-server-certificate
  [--path <value>]
  --server-certificate-name <value>
  --certificate-body <value>
  --private-key <value>
  [--certificate-chain <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--path`` (string)


  The path for the server certificate. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

   

  This parameter is optional. If it is not included, it defaults to a slash (/).

   

  .. note::

    If you are uploading a server certificate specifically for use with Amazon CloudFront distributions, you must specify a path using the ``--path`` option. The path must begin with ``/cloudfront`` and must include a trailing slash (for example, ``/cloudfront/test/`` ). 

  

``--server-certificate-name`` (string)


  The name for the server certificate. Do not include the path in this value. The name of the certificate cannot contain any spaces.

  

``--certificate-body`` (string)


  The contents of the public key certificate in PEM-encoded format.

  

``--private-key`` (string)


  The contents of the private key in PEM-encoded format.

  

``--certificate-chain`` (string)


  The contents of the certificate chain. This is typically a concatenation of the PEM-encoded public key certificates of the chain. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To upload a server certificate to your AWS account**

The following **upload-server-certificate** command uploads a server certificate to your AWS account::

  aws iam upload-server-certificate --server-certificate-name myServerCertificate --certificate-body file://public_key_cert_file.pem --private-key file://my_private_key.pem --certificate-chain file://my_certificate_chain_file.pem

The certificate is in the file ``public_key_cert_file.pem``, and your private key is in the file ``my_private_key.pem``.
When the file has finished uploading, it is available under the name *myServerCertificate*. The certificate chain
provided by the certificate authority (CA) is included as the ``my_certificate_chain_file.pem`` file.

Note that the parameters that contain file names are preceded with ``file://``. This tells the command that the
parameter value is a file name. You can include a complete path following ``file://``.

For more information, see `Creating, Uploading, and Deleting Server Certificates`_ in the *Using IAM* guide.

.. _`Creating, Uploading, and Deleting Server Certificates`: http://docs.aws.amazon.com/IAM/latest/UserGuide/InstallCert.html



======
Output
======

ServerCertificateMetadata -> (structure)

  

  The meta information of the uploaded server certificate without its certificate body, certificate chain, and private key. 

  

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

    

    

  



.. _Working with Server Certificates: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_server-certs.html
.. _Calling the API by Making HTTP Query Requests: http://docs.aws.amazon.com/IAM/latest/UserGuide/programming.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Signing AWS API Requests: http://docs.aws.amazon.com/general/latest/gr/signing_aws_api_requests.html
.. _Limitations on IAM Entities and Objects: http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_iam-limits.html
