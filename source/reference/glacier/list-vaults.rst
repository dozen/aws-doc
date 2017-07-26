[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier list-vaults:


***********
list-vaults
***********



===========
Description
===========



This operation lists all vaults owned by the calling user's account. The list returned in the response is ASCII-sorted by vault name. 

 

By default, this operation returns up to 1,000 items. If there are more vaults to list, the response ``marker`` field contains the vault Amazon Resource Name (ARN) at which to continue the list with a new List Vaults request; otherwise, the ``marker`` field is ``null`` . To return a list of vaults that begins at a specific vault, set the ``marker`` request parameter to the vault ARN you obtained from a previous List Vaults request. You can also limit the number of vaults returned in the response by specifying the ``limit`` parameter in the request. 

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM)`_ .

 

For conceptual information and underlying REST API, go to `Retrieving Vault Metadata in Amazon Glacier`_ and `List Vaults`_ in the *Amazon Glacier Developer Guide* . 



``list-vaults`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``VaultList``


========
Synopsis
========

::

    list-vaults
  --account-id <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID. This value must match the AWS account ID associated with the credentials used to sign the request. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you specify your account ID, do not include any hyphens (apos-apos) in the ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON limit provided. The JSON limit follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (string)
 

  The size of each page.

   

  

  

``--max-items`` (string)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command lists the vaults in the default account and region::

  aws glacier list-vaults --account-id -

Output::

  {
      "VaultList": [
          {
              "SizeInBytes": 3178496,
              "VaultARN": "arn:aws:glacier:us-west-2:0123456789012:vaults/my-vault",
              "LastInventoryDate": "2015-04-07T00:26:19.028Z",
              "VaultName": "my-vault",
              "NumberOfArchives": 1,
              "CreationDate": "2015-04-06T21:23:45.708Z"
          }
      ]
  }

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.

======
Output
======

VaultList -> (list)

  

  List of vaults.

  

  (structure)

    

    Contains the Amazon Glacier response to your request.

    

    VaultARN -> (string)

      

      The Amazon Resource Name (ARN) of the vault.

      

      

    VaultName -> (string)

      

      The name of the vault.

      

      

    CreationDate -> (string)

      

      The UTC date when the vault was created. A limit representation of ISO 8601 date format, for example, "2012-03-20T17:03:43.221Z".

      

      

    LastInventoryDate -> (string)

      

      The UTC date when Amazon Glacier completed the last vault inventory. A limit representation of ISO 8601 date format, for example, "2012-03-20T17:03:43.221Z".

      

      

    NumberOfArchives -> (long)

      

      The number of archives in the vault as of the last inventory date. This field will return ``null`` if an inventory has not yet run on the vault, for example, if you just created the vault.

      

      

    SizeInBytes -> (long)

      

      Total size, in bytes, of the archives in the vault as of the last inventory date. This field will return null if an inventory has not yet run on the vault, for example, if you just created the vault.

      

      

    

  

Marker -> (string)

  

  The vault ARN at which to continue pagination of the results. You use the marker in another List Vaults request to obtain more vaults in the list.

  

  



.. _Access Control Using AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html
.. _List Vaults: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-vaults-get.html
.. _Retrieving Vault Metadata in Amazon Glacier: http://docs.aws.amazon.com/amazonglacier/latest/dev/retrieving-vault-info.html
