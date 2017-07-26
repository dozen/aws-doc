[ :ref:`aws <cli:aws>` . :ref:`elastictranscoder <cli:aws elastictranscoder>` . :ref:`wait <cli:aws elastictranscoder wait>` ]

.. _cli:aws elastictranscoder wait job-complete:


************
job-complete
************



===========
Description
===========

Wait until JMESPath query Job.Status returns Complete when polling with ``read-job``. It will poll every 30 seconds until a successful state has been reached. This will exit with a return code of 255 after 120 failed checks.

========
Synopsis
========

::

    job-complete
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The identifier of the job for which you want to get detailed information.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None