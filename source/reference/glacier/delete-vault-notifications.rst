[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier delete-vault-notifications:


**************************
delete-vault-notifications
**************************



===========
Description
===========



This operation deletes the notification configuration set for a vault. The operation is eventually consistent; that is, it might take some time for Amazon Glacier to completely disable the notifications and you might still receive some notifications for a short time after you send the delete request. 

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM)`_ .

 

For conceptual information and underlying REST API, go to `Configuring Vault Notifications in Amazon Glacier`_ and `Delete Vault Notification Configuration`_ in the Amazon Glacier Developer Guide. 



========
Synopsis
========

::

    delete-vault-notifications
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



======
Output
======

None

.. _Configuring Vault Notifications in Amazon Glacier: http://docs.aws.amazon.com/amazonglacier/latest/dev/configuring-notifications.html
.. _Access Control Using AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/latest/dev/using-iam-with-amazon-glacier.html
.. _Delete Vault Notification Configuration: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-vault-notifications-delete.html
