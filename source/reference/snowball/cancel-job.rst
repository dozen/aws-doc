[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball cancel-job:


**********
cancel-job
**********



===========
Description
===========



Cancels the specified job. You can only cancel a job before its ``JobState`` value changes to ``PreparingAppliance`` . Requesting the ``list-jobs`` or ``describe-job`` action will return a job's ``JobState`` as part of the response element data returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/CancelJob>`_


========
Synopsis
========

::

    cancel-job
  --job-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)


  The 39-character job ID for the job that you want to cancel, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

