[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront delete-streaming-distribution:


*****************************
delete-streaming-distribution
*****************************



===========
Description
===========

Delete a streaming distribution.

.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    delete-streaming-distribution
  --id <value>
  [--if-match <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)
The distribution id.

``--if-match`` (string)
The value of the ETag header you received when you disabled the streaming distribution. For example: E2QWRUHAPOMQZL.

``--cli-input-json`` (string)
Performs service operation based on the JSON if-match provided. The JSON if-match follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None