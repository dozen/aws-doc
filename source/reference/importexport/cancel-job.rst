[ :ref:`aws <cli:aws>` . :ref:`importexport <cli:aws importexport>` ]

.. _cli:aws importexport cancel-job:


**********
cancel-job
**********



===========
Description
===========

This operation cancels a specified job. Only the job owner can cancel it. The operation fails if the job has already started or is complete.

========
Synopsis
========

::

    cancel-job
  --job-id <value>
  [--api-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--job-id`` (string)
A unique identifier which refers to a particular job.

``--api-version`` (string)
Specifies the version of the client tool.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command cancels the specified job::

  aws importexport cancel-job --job-id EX1ID

Only jobs that were created by the AWS account you're currently using can be canceled. Jobs that have already completed cannot be canceled.


======
Output
======

Success -> (boolean)

  Specifies whether (true) or not (false) AWS Import/Export updated your job.

  

