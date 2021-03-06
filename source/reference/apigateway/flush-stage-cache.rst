[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway flush-stage-cache:


*****************
flush-stage-cache
*****************



===========
Description
===========



Flushes a stage's cache.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/FlushStageCache>`_


========
Synopsis
========

::

    flush-stage-cache
  --rest-api-id <value>
  --stage-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--stage-name`` (string)


  The name of the stage to flush its cache.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To flush the cache for an API's stage**

Command::

  aws apigateway flush-stage-cache --rest-api-id 1234123412 --stage-name dev


======
Output
======

None