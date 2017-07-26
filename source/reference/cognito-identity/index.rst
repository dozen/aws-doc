[ :ref:`aws <cli:aws>` ]

.. _cli:aws cognito-identity:


****************
cognito-identity
****************



===========
Description
===========

 

Amazon Cognito is a web service that delivers scoped temporary credentials to mobile devices and other untrusted environments. Amazon Cognito uniquely identifies a device and supplies the user with a consistent identity over the lifetime of an application.

 

Using Amazon Cognito, you can enable authentication with one or more third-party identity providers (Facebook, Google, or Login with Amazon), and you can also choose to support unauthenticated access from your app. Cognito delivers a unique identifier for each user and acts as an OpenID token provider trusted by AWS Security Token Service (STS) to access temporary, limited-privilege AWS credentials.

 

To provide end-user credentials, first make an unsigned call to  get-id . If the end user is authenticated with one of the supported identity providers, set the ``Logins`` map with the identity provider token. ``get-id`` returns a unique identifier for the user.

 

Next, make an unsigned call to  get-credentials-for-identity . This call expects the same ``Logins`` map as the ``get-id`` call, as well as the ``IdentityID`` originally returned by ``get-id`` . Assuming your identity pool has been configured via the  set-identity-pool-roles operation, ``get-credentials-for-identity`` will return AWS credentials for your use. If your pool has not been configured with ``set-identity-pool-roles`` , or if you want to follow legacy flow, make an unsigned call to  get-open-id-token , which returns the OpenID token necessary to call STS and retrieve AWS credentials. This call expects the same ``Logins`` map as the ``get-id`` call, as well as the ``IdentityID`` originally returned by ``get-id`` . The token returned by ``get-open-id-token`` can be passed to the STS operation `AssumeRoleWithWebIdentity <http://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRoleWithWebIdentity.html>`_ to retrieve AWS credentials.

 

If you want to use Amazon Cognito in an Android, iOS, or Unity application, you will probably want to make API calls via the AWS Mobile SDK. To learn more, see the `AWS Mobile SDK Developer Guide <http://docs.aws.amazon.com/mobile/index.html>`_ .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  create-identity-pool
  delete-identities
  delete-identity-pool
  describe-identity
  describe-identity-pool
  get-credentials-for-identity
  get-id
  get-identity-pool-roles
  get-open-id-token
  get-open-id-token-for-developer-identity
  list-identities
  list-identity-pools
  lookup-developer-identity
  merge-developer-identities
  set-identity-pool-roles
  unlink-developer-identity
  unlink-identity
  update-identity-pool
