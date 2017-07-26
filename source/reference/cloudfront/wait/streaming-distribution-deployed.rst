[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` . :ref:`wait <cli:aws cloudfront wait>` ]

.. _cli:aws cloudfront wait streaming-distribution-deployed:


*******************************
streaming-distribution-deployed
*******************************



===========
Description
===========

Wait until a streaming distribution is deployed. It will poll every 60 seconds until a successful state has been reached. This will exit with a return code of 255 after 25 failed checks.

.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    streaming-distribution-deployed
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)
The streaming distribution's id.

``--cli-input-json`` (string)
Performs service operation based on the JSON id provided. The JSON id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None