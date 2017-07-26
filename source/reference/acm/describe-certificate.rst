[ :ref:`aws <cli:aws>` . :ref:`acm <cli:aws acm>` ]

.. _cli:aws acm describe-certificate:


********************
describe-certificate
********************



===========
Description
===========



Returns detailed metadata about the specified ACM Certificate.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/acm-2015-12-08/DescribeCertificate>`_


========
Synopsis
========

::

    describe-certificate
  --certificate-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-arn`` (string)


  The Amazon Resource Name (ARN) of the ACM Certificate. The ARN must have the following form:

   

   ``arn:aws:acm:region:123456789012:certificate/12345678-1234-1234-1234-123456789012``  

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To retrieve the fields contained in an ACM certificate**

The following ``describe-certificate`` command retrieves all of the fields for the certificate with the specified ARN::

  aws acm describe-certificate --certificate-arn arn:aws:acm:us-east-1:123456789012:certificate/12345678-1234-1234-1234-123456789012
 
Output similar to the following is displayed::

  {
    "Certificate": {
      "CertificateArn": "arn:aws:acm:us-east-1:123456789012:certificate/12345678-1234-1234-1234-123456789012", 
      "CreatedAt": 1446835267.0, 
      "DomainName": "www.example.com", 
      "DomainValidationOptions": [
        {
          "DomainName": "www.example.com", 
          "ValidationDomain": "www.example.com", 
          "ValidationEmails": [
            "hostmaster@example.com", 
            "admin@example.com", 
            "owner@example.com.whoisprivacyservice.org", 
            "tech@example.com.whoisprivacyservice.org", 
            "admin@example.com.whoisprivacyservice.org", 
            "postmaster@example.com", 
            "webmaster@example.com", 
            "administrator@example.com"
          ]
        }, 
        {
          "DomainName": "www.example.net", 
          "ValidationDomain": "www.example.net", 
          "ValidationEmails": [
            "postmaster@example.net", 
            "admin@example.net", 
            "owner@example.net.whoisprivacyservice.org", 
            "tech@example.net.whoisprivacyservice.org", 
            "admin@example.net.whoisprivacyservice.org", 
            "hostmaster@example.net", 
            "administrator@example.net", 
            "webmaster@example.net"
          ]
        }
      ], 
      "InUseBy": [], 
      "IssuedAt": 1446835815.0, 
      "Issuer": "Amazon", 
      "KeyAlgorithm": "RSA-2048", 
      "NotAfter": 1478433600.0, 
      "NotBefore": 1446768000.0, 
      "Serial": "0f:ac:b0:a3:8d:ea:65:52:2d:7d:01:3a:39:36:db:d6", 
      "SignatureAlgorithm": "SHA256WITHRSA", 
      "Status": "ISSUED", 
      "Subject": "CN=www.example.com", 
      "SubjectAlternativeNames": [
        "www.example.com", 
        "www.example.net"
      ]
    }
  }


======
Output
======

Certificate -> (structure)

  

  Metadata about an ACM certificate.

  

  CertificateArn -> (string)

    

    The Amazon Resource Name (ARN) of the certificate. For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* .

    

    

  DomainName -> (string)

    

    The fully qualified domain name for the certificate, such as www.example.com or example.com.

    

    

  SubjectAlternativeNames -> (list)

    

    One or more domain names (subject alternative names) included in the certificate. This list contains the domain names that are bound to the public key that is contained in the certificate. The subject alternative names include the canonical domain name (CN) of the certificate and additional domain names that can be used to connect to the website.

    

    (string)

      

      

    

  DomainValidationOptions -> (list)

    

    Contains information about the initial validation of each domain name that occurs as a result of the  request-certificate request. This field exists only when the certificate type is ``AMAZON_ISSUED`` .

    

    (structure)

      

      Contains information about the validation of each domain name in the certificate.

      

      DomainName -> (string)

        

        A fully qualified domain name (FQDN) in the certificate. For example, ``www.example.com`` or ``example.com`` .

        

        

      ValidationEmails -> (list)

        

        A list of email addresses that ACM used to send domain validation emails.

        

        (string)

          

          

        

      ValidationDomain -> (string)

        

        The domain name that ACM used to send domain validation emails.

        

        

      ValidationStatus -> (string)

        

        The validation status of the domain name.

        

        

      

    

  Serial -> (string)

    

    The serial number of the certificate.

    

    

  Subject -> (string)

    

    The name of the entity that is associated with the public key contained in the certificate.

    

    

  Issuer -> (string)

    

    The name of the certificate authority that issued and signed the certificate.

    

    

  CreatedAt -> (timestamp)

    

    The time at which the certificate was requested. This value exists only when the certificate type is ``AMAZON_ISSUED`` .

    

    

  IssuedAt -> (timestamp)

    

    The time at which the certificate was issued. This value exists only when the certificate type is ``AMAZON_ISSUED`` .

    

    

  ImportedAt -> (timestamp)

    

    The date and time at which the certificate was imported. This value exists only when the certificate type is ``IMPORTED`` .

    

    

  Status -> (string)

    

    The status of the certificate.

    

    

  RevokedAt -> (timestamp)

    

    The time at which the certificate was revoked. This value exists only when the certificate status is ``REVOKED`` .

    

    

  RevocationReason -> (string)

    

    The reason the certificate was revoked. This value exists only when the certificate status is ``REVOKED`` .

    

    

  NotBefore -> (timestamp)

    

    The time before which the certificate is not valid.

    

    

  NotAfter -> (timestamp)

    

    The time after which the certificate is not valid.

    

    

  KeyAlgorithm -> (string)

    

    The algorithm that was used to generate the key pair (the public and private key).

    

    

  SignatureAlgorithm -> (string)

    

    The algorithm that was used to sign the certificate.

    

    

  InUseBy -> (list)

    

    A list of ARNs for the AWS resources that are using the certificate. A certificate can be used by multiple AWS resources.

    

    (string)

      

      

    

  FailureReason -> (string)

    

    The reason the certificate request failed. This value exists only when the certificate status is ``FAILED`` . For more information, see `Certificate Request Failed <http://docs.aws.amazon.com/acm/latest/userguide/troubleshooting.html#troubleshooting-failed>`_ in the *AWS Certificate Manager User Guide* .

    

    

  Type -> (string)

    

    The source of the certificate. For certificates provided by ACM, this value is ``AMAZON_ISSUED`` . For certificates that you imported with  import-certificate , this value is ``IMPORTED`` . ACM does not provide `managed renewal <http://docs.aws.amazon.com/acm/latest/userguide/acm-renewal.html>`_ for imported certificates. For more information about the differences between certificates that you import and those that ACM provides, see `Importing Certificates <http://docs.aws.amazon.com/acm/latest/userguide/import-certificate.html>`_ in the *AWS Certificate Manager User Guide* .

    

    

  RenewalSummary -> (structure)

    

    Contains information about the status of ACM's `managed renewal <http://docs.aws.amazon.com/acm/latest/userguide/acm-renewal.html>`_ for the certificate. This field exists only when the certificate type is ``AMAZON_ISSUED`` .

    

    RenewalStatus -> (string)

      

      The status of ACM's `managed renewal <http://docs.aws.amazon.com/acm/latest/userguide/acm-renewal.html>`_ of the certificate.

      

      

    DomainValidationOptions -> (list)

      

      Contains information about the validation of each domain name in the certificate, as it pertains to ACM's `managed renewal <http://docs.aws.amazon.com/acm/latest/userguide/acm-renewal.html>`_ . This is different from the initial validation that occurs as a result of the  request-certificate request. This field exists only when the certificate type is ``AMAZON_ISSUED`` .

      

      (structure)

        

        Contains information about the validation of each domain name in the certificate.

        

        DomainName -> (string)

          

          A fully qualified domain name (FQDN) in the certificate. For example, ``www.example.com`` or ``example.com`` .

          

          

        ValidationEmails -> (list)

          

          A list of email addresses that ACM used to send domain validation emails.

          

          (string)

            

            

          

        ValidationDomain -> (string)

          

          The domain name that ACM used to send domain validation emails.

          

          

        ValidationStatus -> (string)

          

          The validation status of the domain name.

          

          

        

      

    

  

