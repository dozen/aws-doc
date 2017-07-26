[ :ref:`aws <cli:aws>` ]

.. _cli:aws kms:


***
kms
***



===========
Description
===========

 

AWS Key Management Service (AWS KMS) is an encryption and key management web service. This guide describes the AWS KMS operations that you can call programmatically. For general information about AWS KMS, see the `AWS Key Management Service Developer Guide <http://docs.aws.amazon.com/kms/latest/developerguide/>`_ .

 

.. note::

   

  AWS provides SDKs that consist of libraries and sample code for various programming languages and platforms (Java, Ruby, .Net, iOS, Android, etc.). The SDKs provide a convenient way to create programmatic access to AWS KMS and other AWS services. For example, the SDKs take care of tasks such as signing requests (see below), managing errors, and retrying requests automatically. For more information about the AWS SDKs, including how to download and install them, see `Tools for Amazon Web Services <http://aws.amazon.com/tools/>`_ .

   

 

We recommend that you use the AWS SDKs to make programmatic API calls to AWS KMS.

 

Clients must support TLS (Transport Layer Security) 1.0. We recommend TLS 1.2. Clients must also support cipher suites with Perfect Forward Secrecy (PFS) such as Ephemeral Diffie-Hellman (DHE) or Elliptic Curve Ephemeral Diffie-Hellman (ECDHE). Most modern systems such as Java 7 and later support these modes.

 

 **Signing Requests**  

 

Requests must be signed by using an access key ID and a secret access key. We strongly recommend that you *do not* use your AWS account (root) access key ID and secret key for everyday work with AWS KMS. Instead, use the access key ID and secret access key for an IAM user, or you can use the AWS Security Token Service to generate temporary security credentials that you can use to sign requests.

 

All AWS KMS operations require `Signature Version 4 <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

 

 **Logging API Requests**  

 

AWS KMS supports AWS CloudTrail, a service that logs AWS API calls and related events for your AWS account and delivers them to an Amazon S3 bucket that you specify. By using the information collected by CloudTrail, you can determine what requests were made to AWS KMS, who made the request, when it was made, and so on. To learn more about CloudTrail, including how to turn it on and find your log files, see the `AWS CloudTrail User Guide <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/>`_ .

 

 **Additional Resources**  

 

For more information about credentials and request signing, see the following:

 

 
* `AWS Security Credentials <http://docs.aws.amazon.com/general/latest/gr/aws-security-credentials.html>`_ - This topic provides general information about the types of credentials used for accessing AWS. 
 
* `Temporary Security Credentials <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html>`_ - This section of the *IAM User Guide* describes how to create and use temporary security credentials. 
 
* `Signature Version 4 Signing Process <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ - This set of topics walks you through the process of signing a request using an access key ID and a secret access key. 
 

 

 **Commonly Used APIs**  

 

Of the APIs discussed in this guide, the following will prove the most useful for most applications. You will likely perform actions other than these, such as creating keys and assigning policies, by using the console.

 

 
*  encrypt   
 
*  decrypt   
 
*  generate-data-key   
 
*  generate-data-key-without-plaintext   
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  cancel-key-deletion
  create-alias
  create-grant
  create-key
  decrypt
  delete-alias
  delete-imported-key-material
  describe-key
  disable-key
  disable-key-rotation
  enable-key
  enable-key-rotation
  encrypt
  generate-data-key
  generate-data-key-without-plaintext
  generate-random
  get-key-policy
  get-key-rotation-status
  get-parameters-for-import
  import-key-material
  list-aliases
  list-grants
  list-key-policies
  list-keys
  list-resource-tags
  list-retirable-grants
  put-key-policy
  re-encrypt
  retire-grant
  revoke-grant
  schedule-key-deletion
  tag-resource
  untag-resource
  update-alias
  update-key-description
