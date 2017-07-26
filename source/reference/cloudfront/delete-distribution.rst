[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront delete-distribution:


*******************
delete-distribution
*******************



===========
Description
===========

Delete a distribution.

.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    delete-distribution
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
The value of the ETag header you received when you disabled the distribution. For example: E2QWRUHAPOMQZL.

``--cli-input-json`` (string)
Performs service operation based on the JSON if-match provided. The JSON if-match follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command deletes a CloudFront distribution with the ID ``S11A16G5KZMEQD``::

  aws cloudfront delete-distribution --id S11A16G5KZMEQD --if-match 8UBQECEJX24ST

The distribution ID is available in the output of ``create-distribution`` and ``list-distributions``. The distribution must be disabled with ``update-distribution`` prior to deletion. The ETag value ``8UBQECEJX24ST`` for the ``if-match`` parameter is available in the output of ``update-distribution``, ``get-distribution`` or ``get-distribution-config``.

======
Output
======

None