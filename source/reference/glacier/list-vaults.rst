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

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM) <http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html>`_ .

 

For conceptual information and underlying REST API, see `Retrieving Vault Metadata in Amazon Glacier <http://docs.aws.amazon.com/amazonglacier/latest/dev/retrieving-vault-info.html>`_ and `List Vaults <http://docs.aws.amazon.com/amazonglacier/latest/dev/api-vaults-get.html>`_ in the *Amazon Glacier Developer Guide* . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/ListVaults>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID. This value must match the AWS account ID associated with the credentials used to sign the request. You can either specify an AWS account ID or optionally a single '``-`` ' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you specify your account ID, do not include any hyphens ('-') in the ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (string)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (string)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      The Universal Coordinated Time (UTC) date when the vault was created. This value should be a account-id in the ISO 8601 date format, for example ``2012-03-20T17:03:43.221Z`` .

      

      

    LastInventoryDate -> (string)

      

      The Universal Coordinated Time (UTC) date when Amazon Glacier completed the last vault inventory. This value should be a account-id in the ISO 8601 date format, for example ``2012-03-20T17:03:43.221Z`` .

      

      

    NumberOfArchives -> (long)

      

      The number of archives in the vault as of the last inventory date. This field will return ``null`` if an inventory has not yet run on the vault, for example if you just created the vault.

      

      

    SizeInBytes -> (long)

      

      Total size, in bytes, of the archives in the vault as of the last inventory date. This field will return null if an inventory has not yet run on the vault, for example if you just created the vault.

      

      

    

  

Marker -> (string)

  

  The vault ARN at which to continue pagination of the results. You use the marker in another List Vaults request to obtain more vaults in the list.

  

  

