[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier set-vault-notifications:


***********************
set-vault-notifications
***********************



===========
Description
===========



This operation configures notifications that will be sent when specific events happen to a vault. By default, you don't get any notifications. 

 

To configure vault notifications, send a PUT request to the ``notification-configuration`` subresource of the vault. The request should include a JSON document that provides an Amazon SNS topic and specific events for which you want Amazon Glacier to send notifications to the topic.

 

Amazon SNS topics must grant permission to the vault to be allowed to publish notifications to the topic. You can configure a vault to publish a notification for the following vault events:

 

 
* **ArchiveRetrievalCompleted** This event occurs when a job that was initiated for an archive retrieval is completed ( initiate-job ). The status of the completed job can be "Succeeded" or "Failed". The notification sent to the SNS topic is the same output as returned from  describe-job . 
 
* **InventoryRetrievalCompleted** This event occurs when a job that was initiated for an inventory retrieval is completed ( initiate-job ). The status of the completed job can be "Succeeded" or "Failed". The notification sent to the SNS topic is the same output as returned from  describe-job . 
 

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM)`_ .

 

For conceptual information and underlying REST API, go to `Configuring Vault Notifications in Amazon Glacier`_ and `Set Vault Notification Configuration`_ in the *Amazon Glacier Developer Guide* . 



========
Synopsis
========

::

    set-vault-notifications
  --account-id <value>
  --vault-name <value>
  [--vault-notification-config <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens (apos-apos) in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--vault-notification-config`` (structure)


  Provides options for specifying notification configuration.

  



Shorthand Syntax::

    SNSTopic=string,Events=string,string




JSON Syntax::

  {
    "SNSTopic": "string",
    "Events": ["string", ...]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON vault-name provided. The JSON vault-name follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command configures SNS notifications for a vault named ``my-vault``::

  aws glacier set-vault-notifications --account-id - --vault-name my-vault --vault-notification-config file://notificationconfig.json

``notificationconfig.json`` is a JSON file in the current folder that specifies an SNS topic and the events to publish::

  {
    "SNSTopic": "arn:aws:sns:us-west-2:0123456789012:my-vault",
    "Events": ["ArchiveRetrievalCompleted", "InventoryRetrievalCompleted"]
  }

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.

======
Output
======

None

.. _Configuring Vault Notifications in Amazon Glacier: http://docs.aws.amazon.com/amazonglacier/latest/dev/configuring-notifications.html
.. _Access Control Using AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html
.. _Set Vault Notification Configuration: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-vault-notifications-put.html
