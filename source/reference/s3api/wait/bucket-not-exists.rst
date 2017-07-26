[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` . :ref:`wait <cli:aws s3api wait>` ]

.. _cli:aws s3api wait bucket-not-exists:


*****************
bucket-not-exists
*****************



===========
Description
===========

Wait until 404 response is received when polling with ``head-bucket``. It will poll every 5 seconds until a successful state has been reached. This will exit with a return code of 255 after 20 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/HeadBucket>`_


========
Synopsis
========

::

    bucket-not-exists
  --bucket <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None