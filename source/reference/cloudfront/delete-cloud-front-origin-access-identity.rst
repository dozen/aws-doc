[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront delete-cloud-front-origin-access-identity:


*****************************************
delete-cloud-front-origin-access-identity
*****************************************



===========
Description
===========



Delete an origin access identity. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/DeleteCloudFrontOriginAccessIdentity>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    delete-cloud-front-origin-access-identity
  --id <value>
  [--if-match <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The origin access identity's ID.

  

``--if-match`` (string)


  The value of the ``ETag`` header you received from a previous ``GET`` or ``PUT`` request. For example: ``E2QWRUHAPOMQZL`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON id provided. The JSON id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None