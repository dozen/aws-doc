[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball get-job-unlock-code:


*******************
get-job-unlock-code
*******************



===========
Description
===========



Returns the ``UnlockCode`` code value for the specified job. A particular ``UnlockCode`` value can be accessed for up to 90 days after the associated job has been created.

 

The ``UnlockCode`` value is a 29-character code with 25 alphanumeric characters and 4 hyphens. This code is used to decrypt the manifest file when it is passed along with the manifest to the Snowball through the Snowball client when the client is started for the first time.

 

As a best practice, we recommend that you don't save a copy of the ``UnlockCode`` in the same location as the manifest file for that job. Saving these separately helps prevent unauthorized parties from gaining access to the Snowball associated with that job.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/GetJobUnlockCode>`_


========
Synopsis
========

::

    get-job-unlock-code
  --job-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)


  The ID for the job that you want to get the ``UnlockCode`` value for, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

UnlockCode -> (string)

  

  The ``UnlockCode`` value for the specified job. The ``UnlockCode`` value can be accessed for up to 90 days after the job has been created.

  

  

