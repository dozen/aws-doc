[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` . :ref:`wait <cli:aws cloudfront wait>` ]

.. _cli:aws cloudfront wait invalidation-completed:


**********************
invalidation-completed
**********************



===========
Description
===========

Wait until an invalidation has completed. It will poll every 20 seconds until a successful state has been reached. This will exit with a return code of 255 after 60 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/GetInvalidation>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    invalidation-completed
  --distribution-id <value>
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--distribution-id`` (string)


  The distribution's ID.

  

``--id`` (string)


  The identifier for the invalidation request, for example, ``IDFDVBD632BHDS5`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON distribution-id provided. The JSON distribution-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None