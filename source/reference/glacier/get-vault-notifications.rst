[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier get-vault-notifications:


***********************
get-vault-notifications
***********************



===========
Description
===========



This operation retrieves the ``notification-configuration`` subresource of the specified vault.

 

For information about setting a notification configuration on a vault, see  set-vault-notifications . If a notification configuration for a vault is not set, the operation returns a ``404 Not Found`` error. For more information about vault notifications, see `Configuring Vault Notifications in Amazon Glacier`_ . 

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM)`_ .

 

For conceptual information and underlying REST API, go to `Configuring Vault Notifications in Amazon Glacier`_ and `Get Vault Notification Configuration`_ in the *Amazon Glacier Developer Guide* . 



========
Synopsis
========

::

    get-vault-notifications
  --account-id <value>
  --vault-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens (apos-apos) in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON vault-name provided. The JSON vault-name follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command gets a description of the notification configuration for a vault named ``my-vault``::

  aws glacier get-vault-notifications --account-id - --vault-name my-vault

Output::

  {
      "vaultNotificationConfig": {
          "Events": [
              "InventoryRetrievalCompleted",
              "ArchiveRetrievalCompleted"
          ],
          "SNSTopic": "arn:aws:sns:us-west-2:0123456789012:my-vault"
      }
  }

If no notifications have been configured for the vault, an error is returned. Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.


======
Output
======

vaultNotificationConfig -> (structure)

  

  Returns the notification configuration set on the vault.

  

  SNSTopic -> (string)

    

    The Amazon Simple Notification Service (Amazon SNS) topic Amazon Resource Name (ARN).

    

    

  Events -> (list)

    

    A list of one or more events for which Amazon Glacier will send a notification to the specified Amazon SNS topic.

    

    (string)

      

      

    

  



.. _Configuring Vault Notifications in Amazon Glacier: http://docs.aws.amazon.com/amazonglacier/latest/dev/configuring-notifications.html
.. _Access Control Using AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html
.. _Get Vault Notification Configuration: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-vault-notifications-get.html
