[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier delete-archive:


**************
delete-archive
**************



===========
Description
===========



This operation deletes an archive from a vault. Subsequent requests to initiate a retrieval of this archive will fail. Archive retrievals that are in progress for this archive ID may or may not succeed according to the following scenarios:

 

 
* If the archive retrieval job is actively preparing the data for download when Amazon Glacier receives the delete archive request, the archival retrieval operation might fail. 
 
* If the archive retrieval job has successfully prepared the archive for download when Amazon Glacier receives the delete archive request, you will be able to download the output. 
 

 

This operation is idempotent. Attempting to delete an already-deleted archive does not result in an error.

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM) <http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html>`_ .

 

For conceptual information and underlying REST API, see `Deleting an Archive in Amazon Glacier <http://docs.aws.amazon.com/amazonglacier/latest/dev/deleting-an-archive.html>`_ and `Delete Archive <http://docs.aws.amazon.com/amazonglacier/latest/dev/api-archive-delete.html>`_ in the *Amazon Glacier Developer Guide* . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/DeleteArchive>`_


========
Synopsis
========

::

    delete-archive
  --account-id <value>
  --vault-name <value>
  --archive-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single '``-`` ' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens ('-') in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--archive-id`` (string)


  The ID of the archive to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None