[ :ref:`aws <cli:aws>` . :ref:`elastictranscoder <cli:aws elastictranscoder>` . :ref:`wait <cli:aws elastictranscoder wait>` ]

.. _cli:aws elastictranscoder wait job-complete:


************
job-complete
************



===========
Description
===========

Wait until JMESPath query Job.Status returns Complete when polling with ``read-job``. It will poll every 30 seconds until a successful state has been reached. This will exit with a return code of 255 after 120 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elastictranscoder-2012-09-25/ReadJob>`_


========
Synopsis
========

::

    job-complete
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The identifier of the job for which you want to get detailed information.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None