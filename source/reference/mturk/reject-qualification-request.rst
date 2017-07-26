[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk reject-qualification-request:


****************************
reject-qualification-request
****************************



===========
Description
===========



The ``reject-qualification-request`` operation rejects a user's request for a Qualification. 

 

You can provide a text message explaining why the request was rejected. The Worker who made the request can see this message.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/RejectQualificationRequest>`_


========
Synopsis
========

::

    reject-qualification-request
  --qualification-request-id <value>
  [--reason <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--qualification-request-id`` (string)


  The ID of the Qualification request, as returned by the ``list-qualification-requests`` operation. 

  

``--reason`` (string)


  A text message explaining why the request was rejected, to be shown to the Worker who made the request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

