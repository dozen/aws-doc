[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier abort-multipart-upload:


**********************
abort-multipart-upload
**********************



===========
Description
===========



This operation aborts a multipart upload identified by the upload ID.

 

After the Abort Multipart Upload request succeeds, you cannot upload any more parts to the multipart upload or complete the multipart upload. Aborting a completed upload fails. However, aborting an already-aborted upload will succeed, for a short time. For more information about uploading a part and completing a multipart upload, see  upload-multipart-part and  complete-multipart-upload .

 

This operation is idempotent.

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM) <http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html>`_ .

 

For conceptual information and underlying REST API, see `Working with Archives in Amazon Glacier <http://docs.aws.amazon.com/amazonglacier/latest/dev/working-with-archives.html>`_ and `Abort Multipart Upload <http://docs.aws.amazon.com/amazonglacier/latest/dev/api-multipart-abort-upload.html>`_ in the *Amazon Glacier Developer Guide* . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/AbortMultipartUpload>`_


========
Synopsis
========

::

    abort-multipart-upload
  --account-id <value>
  --vault-name <value>
  --upload-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single '``-`` ' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens ('-') in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--upload-id`` (string)


  The upload ID of the multipart upload to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command deletes an in-progress multipart upload to a vault named ``my-vault``::

  aws glacier abort-multipart-upload --account-id - --vault-name my-vault --upload-id 19gaRezEXAMPLES6Ry5YYdqthHOC_kGRCT03L9yetr220UmPtBYKk-OssZtLqyFu7sY1_lR7vgFuJV6NtcV5zpsJ

This command does not produce any output. Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account. The upload ID is returned by the ``aws glacier initiate-multipart-upload`` command and can also be obtained by using ``aws glacier list-multipart-uploads``.

For more information on multipart uploads to Amazon Glacier using the AWS CLI, see `Using Amazon Glacier`_ in the *AWS CLI User Guide*.

.. _`Using Amazon Glacier`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-glacier.html

======
Output
======

None