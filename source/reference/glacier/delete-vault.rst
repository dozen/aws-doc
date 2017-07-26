[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier delete-vault:


************
delete-vault
************



===========
Description
===========



This operation deletes a vault. Amazon Glacier will delete a vault only if there are no archives in the vault as of the last inventory and there have been no writes to the vault since the last inventory. If either of these conditions is not satisfied, the vault deletion fails (that is, the vault is not removed) and Amazon Glacier returns an error. You can use  describe-vault to return the number of archives in a vault, and you can use `Initiate a Job (POST jobs)`_ to initiate a new inventory retrieval for a vault. The inventory contains the archive IDs you use to delete archives using `Delete Archive (DELETE archive)`_ .

 

This operation is idempotent.

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM)`_ .

 

For conceptual information and underlying REST API, go to `Deleting a Vault in Amazon Glacier`_ and `Delete Vault`_ in the *Amazon Glacier Developer Guide* . 



========
Synopsis
========

::

    delete-vault
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

The following command deletes a vault named ``my-vault``::

  aws glacier delete-vault --vault-name my-vault --account-id -

This command does not produce any output. Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.

======
Output
======

None

.. _Access Control Using AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html
.. _Deleting a Vault in Amazon Glacier: http://docs.aws.amazon.com/amazonglacier/latest/dev/deleting-vaults.html
.. _Initiate a Job (POST jobs): http://docs.aws.amazon.com/amazonglacier/latest/dev/api-initiate-job-post.html
.. _Delete Vault: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-vault-delete.html
.. _Delete Archive (DELETE archive): http://docs.aws.amazon.com/amazonglacier/latest/dev/api-archive-delete.html
