[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm modify-document-permission:


**************************
modify-document-permission
**************************



===========
Description
===========



Shares a Systems Manager document publicly or privately. If you share a document privately, you must specify the AWS user account IDs for those people who can use the document. If you share a document publicly, you must specify *All* as the account ID.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/ModifyDocumentPermission>`_


========
Synopsis
========

::

    modify-document-permission
  --name <value>
  --permission-type <value>
  [--account-ids-to-add <value>]
  [--account-ids-to-remove <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the document that you want to share.

  

``--permission-type`` (string)


  The permission type for the document. The permission type can be *Share* .

  

  Possible values:

  
  *   ``Share``

  

  

``--account-ids-to-add`` (list)


  The AWS user accounts that should have access to the document. The account IDs can either be a group of account IDs or *All* .

  



Syntax::

  "string" "string" ...



``--account-ids-to-remove`` (list)


  The AWS user accounts that should no longer have access to the document. The AWS user account can either be a group of account IDs or *All* . This action has a higher priority than *AccountIdsToAdd* . If you specify an account ID to add and the same ID to remove, the system removes access to the document.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To modify the permissions for a document**

This example modifies the permissions for a document. There is no output if the command succeeds.

Command::

  aws ssm modify-document-permission --name "RunShellScript" --permission-type "Share" --account-ids-to-add "All"


======
Output
======

