[ :ref:`aws <cli:aws>` ]

.. _cli:aws workdocs:


********
workdocs
********



===========
Description
===========



The WorkDocs API is designed for the following use cases:

 

 
* File Migration: File migration applications are supported for users who want to migrate their files from an on-premise or off-premise file system or service. Users can insert files into a user directory structure, as well as allow for basic metadata changes, such as modifications to the permissions of files. 
 
* Security: Support security applications are supported for users who have additional security needs, such as anti-virus or data loss prevention. The APIs, in conjunction with Amazon CloudTrail, allow these applications to detect when changes occur in Amazon WorkDocs, so the application can take the necessary actions and replace the target file. The application can also choose to email the user if the target file violates the policy. 
 
* eDiscovery/Analytics: General administrative applications are supported, such as eDiscovery and analytics. These applications can choose to mimic and/or record the actions in an Amazon WorkDocs site, in conjunction with Amazon CloudTrails, to replicate data for eDiscovery, backup, or analytical applications. 
 

 

All Amazon WorkDocs APIs are Amazon authenticated, certificate-signed APIs. They not only require the use of the AWS SDK, but also allow for the exclusive use of IAM users and roles to help facilitate access, trust, and permission policies. By creating a role and allowing an IAM user to access the Amazon WorkDocs site, the IAM user gains full administrative visibility into the entire Amazon WorkDocs site (or as set in the IAM policy). This includes, but is not limited to, the ability to modify file permissions and upload any file to any user. This allows developers to perform the three use cases above, as well as give users the ability to grant access on a selective basis using the IAM model.



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  abort-document-version-upload
  activate-user
  add-resource-permissions
  create-comment
  create-custom-metadata
  create-folder
  create-labels
  create-notification-subscription
  create-user
  deactivate-user
  delete-comment
  delete-custom-metadata
  delete-document
  delete-folder
  delete-folder-contents
  delete-labels
  delete-notification-subscription
  delete-user
  describe-activities
  describe-comments
  describe-document-versions
  describe-folder-contents
  describe-notification-subscriptions
  describe-resource-permissions
  describe-root-folders
  describe-users
  get-current-user
  get-document
  get-document-path
  get-document-version
  get-folder
  get-folder-path
  initiate-document-version-upload
  remove-all-resource-permissions
  remove-resource-permission
  update-document
  update-document-version
  update-folder
  update-user
