[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier create-vault:


************
create-vault
************



===========
Description
===========



This operation creates a new vault with the specified name. The name of the vault must be unique within a region for an AWS account. You can create up to 1,000 vaults per account. If you need to create more vaults, contact Amazon Glacier.

 

You must use the following guidelines when naming a vault. 

 

 

 
* Names can be between 1 and 255 characters long.  
 
* Allowed characters are a-z, A-Z, 0-9, '_' (underscore), '-' (hyphen), and '.' (period). 
 

 

 

This operation is idempotent.

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM)`_ .

 

For conceptual information and underlying REST API, go to `Creating a Vault in Amazon Glacier`_ and `Create Vault`_ in the *Amazon Glacier Developer Guide* . 



========
Synopsis
========

::

    create-vault
  --account-id <value>
  --vault-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID. This value must match the AWS account ID associated with the credentials used to sign the request. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you specify your account ID, do not include any hyphens (apos-apos) in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON vault-name provided. The JSON vault-name follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command creates a new vault named ``my-vault``::

  aws glacier create-vault --vault-name my-vault --account-id -

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.

======
Output
======

location -> (string)

  

  The URI of the vault that was created.

  

  



.. _Access Control Using AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html
.. _Create Vault: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-vault-put.html
.. _Creating a Vault in Amazon Glacier: http://docs.aws.amazon.com/amazonglacier/latest/dev/creating-vaults.html
