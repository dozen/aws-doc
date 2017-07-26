[ :ref:`aws <cli:aws>` ]

.. _cli:aws iam:


***
iam
***



===========
Description
===========

 

AWS Identity and Access Management (IAM) is a web service that you can use to manage users and user permissions under your AWS account. This guide provides descriptions of IAM actions that you can call programmatically. For general information about IAM, see `AWS Identity and Access Management (IAM)`_ . For the user guide for IAM, see `Using IAM`_ . 

 

.. note::

  AWS provides SDKs that consist of libraries and sample code for various programming languages and platforms (Java, Ruby, .NET, iOS, Android, etc.). The SDKs provide a convenient way to create programmatic access to IAM and AWS. For example, the SDKs take care of tasks such as cryptographically signing requests (see below), managing errors, and retrying requests automatically. For information about the AWS SDKs, including how to download and install them, see the `Tools for Amazon Web Services`_ page. 

 

We recommend that you use the AWS SDKs to make programmatic API calls to IAM. However, you can also use the IAM Query API to make direct calls to the IAM web service. To learn more about the IAM Query API, see `Making Query Requests`_ in the *Using IAM* guide. IAM supports GET and POST requests for all actions. That is, the API does not require you to use GET for some actions and POST for others. However, GET requests are subject to the limitation size of a URL. Therefore, for operations that require larger sizes, use a POST request. 

 

 **Signing Requests**  

 

Requests must be signed using an access key ID and a secret access key. We strongly recommend that you do not use your AWS account access key ID and secret access key for everyday work with IAM. You can use the access key ID and secret access key for an IAM user or you can use the AWS Security Token Service to generate temporary security credentials and use those to sign requests. 

 

To sign requests, we recommend that you use `Signature Version 4`_ . If you have an existing application that uses Signature Version 2, you do not have to update it to use Signature Version 4. However, some operations now require Signature Version 4. The documentation for operations that require version 4 indicate this requirement. 

 

 **Additional Resources**  

 

For more information, see the following:

 

 
* `AWS Security Credentials`_ . This topic provides general information about the types of credentials used for accessing AWS. 
 
* `IAM Best Practices`_ . This topic presents a list of suggestions for using the IAM service to help secure your AWS resources. 
 
* `Signing AWS API Requests`_ . This set of topics walk you through the process of signing a request using an access key ID and secret access key. 
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  add-client-id-to-open-id-connect-provider
  add-role-to-instance-profile
  add-user-to-group
  attach-group-policy
  attach-role-policy
  attach-user-policy
  change-password
  create-access-key
  create-account-alias
  create-group
  create-instance-profile
  create-login-profile
  create-open-id-connect-provider
  create-policy
  create-policy-version
  create-role
  create-saml-provider
  create-user
  create-virtual-mfa-device
  deactivate-mfa-device
  delete-access-key
  delete-account-alias
  delete-account-password-policy
  delete-group
  delete-group-policy
  delete-instance-profile
  delete-login-profile
  delete-open-id-connect-provider
  delete-policy
  delete-policy-version
  delete-role
  delete-role-policy
  delete-saml-provider
  delete-server-certificate
  delete-signing-certificate
  delete-ssh-public-key
  delete-user
  delete-user-policy
  delete-virtual-mfa-device
  detach-group-policy
  detach-role-policy
  detach-user-policy
  enable-mfa-device
  generate-credential-report
  get-access-key-last-used
  get-account-authorization-details
  get-account-password-policy
  get-account-summary
  get-context-keys-for-custom-policy
  get-context-keys-for-principal-policy
  get-credential-report
  get-group
  get-group-policy
  get-instance-profile
  get-login-profile
  get-open-id-connect-provider
  get-policy
  get-policy-version
  get-role
  get-role-policy
  get-saml-provider
  get-server-certificate
  get-ssh-public-key
  get-user
  get-user-policy
  list-access-keys
  list-account-aliases
  list-attached-group-policies
  list-attached-role-policies
  list-attached-user-policies
  list-entities-for-policy
  list-group-policies
  list-groups
  list-groups-for-user
  list-instance-profiles
  list-instance-profiles-for-role
  list-mfa-devices
  list-open-id-connect-providers
  list-policies
  list-policy-versions
  list-role-policies
  list-roles
  list-saml-providers
  list-server-certificates
  list-signing-certificates
  list-ssh-public-keys
  list-user-policies
  list-users
  list-virtual-mfa-devices
  put-group-policy
  put-role-policy
  put-user-policy
  remove-client-id-from-open-id-connect-provider
  remove-role-from-instance-profile
  remove-user-from-group
  resync-mfa-device
  set-default-policy-version
  simulate-custom-policy
  simulate-principal-policy
  update-access-key
  update-account-password-policy
  update-assume-role-policy
  update-group
  update-login-profile
  update-open-id-connect-provider-thumbprint
  update-saml-provider
  update-server-certificate
  update-signing-certificate
  update-ssh-public-key
  update-user
  upload-server-certificate
  upload-signing-certificate
  upload-ssh-public-key
  wait/index


.. _Signature Version 4: http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html
.. _AWS Identity and Access Management (IAM): http://aws.amazon.com/iam/
.. _IAM Best Practices: http://docs.aws.amazon.com/IAM/latest/UserGuide/IAMBestPractices.html
.. _AWS Security Credentials: http://docs.aws.amazon.com/general/latest/gr/aws-security-credentials.html
.. _Using IAM: http://docs.aws.amazon.com/IAM/latest/UserGuide/
.. _Tools for Amazon Web Services: http://aws.amazon.com/tools/
.. _Signing AWS API Requests: http://docs.aws.amazon.com/general/latest/gr/signing_aws_api_requests.html
.. _Making Query Requests: http://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_UsingQueryAPI.html
