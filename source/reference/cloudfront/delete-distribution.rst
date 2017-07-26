[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront delete-distribution:


*******************
delete-distribution
*******************



===========
Description
===========



Delete a distribution. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/DeleteDistribution>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The distribution ID. 

  

``--if-match`` (string)


  The value of the ``ETag`` header that you received when you disabled the distribution. For example: ``E2QWRUHAPOMQZL`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON id provided. The JSON id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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