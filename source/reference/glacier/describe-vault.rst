[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier describe-vault:


**************
describe-vault
**************



===========
Description
===========



This operation returns information about a vault, including the vault's Amazon Resource Name (ARN), the date the vault was created, the number of archives it contains, and the total size of all the archives in the vault. The number of archives and their total size are as of the last inventory generation. This means that if you add or remove an archive from a vault, and then immediately use Describe Vault, the change in contents will not be immediately reflected. If you want to retrieve the latest inventory of the vault, use  initiate-job . Amazon Glacier generates vault inventories approximately daily. For more information, see `Downloading a Vault Inventory in Amazon Glacier <http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-inventory.html>`_ . 

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM) <http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html>`_ .

 

For conceptual information and underlying REST API, see `Retrieving Vault Metadata in Amazon Glacier <http://docs.aws.amazon.com/amazonglacier/latest/dev/retrieving-vault-info.html>`_ and `Describe Vault <http://docs.aws.amazon.com/amazonglacier/latest/dev/api-vault-get.html>`_ in the *Amazon Glacier Developer Guide* . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/DescribeVault>`_


========
Synopsis
========

::

    describe-vault
  --account-id <value>
  --vault-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single '``-`` ' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens ('-') in the ID. 

  

``--vault-name`` (string)


  The name of the vault.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command retrieves data about a vault named ``my-vault``::

  aws glacier describe-vault --vault-name my-vault --account-id -

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.

======
Output
======

VaultARN -> (string)

  

  The Amazon Resource Name (ARN) of the vault.

  

  

VaultName -> (string)

  

  The name of the vault.

  

  

CreationDate -> (string)

  

  The Universal Coordinated Time (UTC) date when the vault was created. This value should be a account-id in the ISO 8601 date format, for example ``2012-03-20T17:03:43.221Z`` .

  

  

LastInventoryDate -> (string)

  

  The Universal Coordinated Time (UTC) date when Amazon Glacier completed the last vault inventory. This value should be a account-id in the ISO 8601 date format, for example ``2012-03-20T17:03:43.221Z`` .

  

  

NumberOfArchives -> (long)

  

  The number of archives in the vault as of the last inventory date. This field will return ``null`` if an inventory has not yet run on the vault, for example if you just created the vault.

  

  

SizeInBytes -> (long)

  

  Total size, in bytes, of the archives in the vault as of the last inventory date. This field will return null if an inventory has not yet run on the vault, for example if you just created the vault.

  

  

