[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam upload-signing-certificate:


**************************
upload-signing-certificate
**************************



===========
Description
===========



Uploads an X.509 signing certificate and associates it with the specified IAM user. Some AWS services use X.509 signing certificates to validate requests that are signed with a corresponding private key. When you upload the certificate, its default status is ``Active`` .

 

If the ``UserName`` field is not specified, the IAM user name is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users.

 

.. note::

   

  Because the body of a X.509 certificate can be large, you should use POST rather than GET when calling ``upload-signing-certificate`` . For information about setting up signatures and authorization through the API, go to `Signing AWS API Requests <http://docs.aws.amazon.com/general/latest/gr/signing_aws_api_requests.html>`_ in the *AWS General Reference* . For general information about using the Query API with IAM, go to `Making Query Requests <http://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_UsingQueryAPI.html>`_ in the *IAM User Guide* .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UploadSigningCertificate>`_


========
Synopsis
========

::

    upload-signing-certificate
  [--user-name <value>]
  --certificate-body <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the user the signing certificate is for.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--certificate-body`` (string)


  The contents of the signing certificate.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ used to validate this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range as well as the printable characters in the Basic Latin and Latin-1 Supplement character set (through \u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To upload a signing certificate for an IAM user**

The following ``upload-signing-certificate`` command uploads a signing certificate for the IAM user named ``Bob``::

  aws iam upload-signing-certificate --user-name Bob --certificate-body file://certificate.pem

Output::

  {
      "Certificate": {
          "UserName": "Bob",
          "Status": "Active",
          "CertificateBody": "-----BEGIN CERTIFICATE-----<certificate-body>-----END CERTIFICATE-----",
          "CertificateId": "TA7SMP42TDN5Z26OBPJE7EXAMPLE",
          "UploadDate": "2013-06-06T21:40:08.121Z"
      }
  }

The certificate is in a file named *certificate.pem* in PEM format.

For more information, see `Creating and Uploading a User Signing Certificate`_ in the *Using IAM* guide.

.. _`Creating and Uploading a User Signing Certificate`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_UploadCertificate.html



======
Output
======

Certificate -> (structure)

  

  Information about the certificate.

  

  UserName -> (string)

    

    The name of the user the signing certificate is associated with.

    

    

  CertificateId -> (string)

    

    The ID for the signing certificate.

    

    

  CertificateBody -> (string)

    

    The contents of the signing certificate.

    

    

  Status -> (string)

    

    The status of the signing certificate. ``Active`` means the key is valid for API calls, while ``Inactive`` means it is not.

    

    

  UploadDate -> (timestamp)

    

    The date when the signing certificate was uploaded.

    

    

  

