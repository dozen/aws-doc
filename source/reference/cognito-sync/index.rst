[ :ref:`aws <cli:aws>` ]

.. _cli:aws cognito-sync:


************
cognito-sync
************



===========
Description
===========

 

Amazon Cognito Sync provides an AWS service and client library that enable cross-device syncing of application-related user data. High-level client libraries are available for both iOS and Android. You can use these libraries to persist data locally so that it's available even if the device is offline. Developer credentials don't need to be stored on the mobile device to access the service. You can use Amazon Cognito to obtain a normalized user ID and credentials. User data is persisted in a dataset that can store up to 1 MB of key-value pairs, and you can have up to 20 datasets per user identity.

 

With Amazon Cognito Sync, the data stored for each identity is accessible only to credentials assigned to that identity. In order to use the Cognito Sync service, you need to make API calls using credentials retrieved with `Amazon Cognito Identity service <http://docs.aws.amazon.com/cognitoidentity/latest/APIReference/Welcome.html>`_ .

 

If you want to use Cognito Sync in an Android or iOS application, you will probably want to make API calls via the AWS Mobile SDK. To learn more, see the `Developer Guide for Android <http://docs.aws.amazon.com/mobile/sdkforandroid/developerguide/cognito-sync.html>`_ and the `Developer Guide for iOS <http://docs.aws.amazon.com/mobile/sdkforios/developerguide/cognito-sync.html>`_ .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  bulk-publish
  delete-dataset
  describe-dataset
  describe-identity-pool-usage
  describe-identity-usage
  get-bulk-publish-details
  get-cognito-events
  get-identity-pool-configuration
  list-datasets
  list-identity-pool-usage
  list-records
  register-device
  set-cognito-events
  set-identity-pool-configuration
  subscribe-to-dataset
  unsubscribe-from-dataset
  update-records
