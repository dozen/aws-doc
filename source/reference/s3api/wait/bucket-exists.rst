[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` . :ref:`wait <cli:aws s3api wait>` ]

.. _cli:aws s3api wait bucket-exists:


*************
bucket-exists
*************



===========
Description
===========

Wait until 200 response is received when polling with ``head-bucket``. It will poll every 5 seconds until a successful state has been reached. This will exit with a return code of 255 after 20 failed checks.

========
Synopsis
========

::

    bucket-exists
  --bucket <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None