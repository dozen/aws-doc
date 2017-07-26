[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball get-job-manifest:


****************
get-job-manifest
****************



===========
Description
===========



Returns a link to an Amazon S3 presigned URL for the manifest file associated with the specified ``job-id`` value. You can access the manifest file for up to 60 minutes after this request has been made. To access the manifest file after 60 minutes have passed, you'll have to make another call to the ``get-job-manifest`` action.

 

The manifest is an encrypted file that you can download after your job enters the ``WithCustomer`` status. The manifest is decrypted by using the ``UnlockCode`` code value, when you pass both values to the Snowball through the Snowball client when the client is started for the first time.

 

As a best practice, we recommend that you don't save a copy of an ``UnlockCode`` value in the same location as the manifest file for that job. Saving these separately helps prevent unauthorized parties from gaining access to the Snowball associated with that job.

 

The credentials of a given job, including its manifest file and unlock code, expire 90 days after the job is created.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/GetJobManifest>`_


========
Synopsis
========

::

    get-job-manifest
  --job-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)


  The ID for a job that you want to get the manifest file for, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ManifestURI -> (string)

  

  The Amazon S3 presigned URL for the manifest file associated with the specified ``job-id`` value.

  

  

