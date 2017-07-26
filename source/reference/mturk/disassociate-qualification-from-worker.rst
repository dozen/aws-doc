[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk disassociate-qualification-from-worker:


**************************************
disassociate-qualification-from-worker
**************************************



===========
Description
===========



The ``disassociate-qualification-from-worker`` revokes a previously granted Qualification from a user. 

 

You can provide a text message explaining why the Qualification was revoked. The user who had the Qualification can see this message. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/DisassociateQualificationFromWorker>`_


========
Synopsis
========

::

    disassociate-qualification-from-worker
  --worker-id <value>
  --qualification-type-id <value>
  [--reason <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--worker-id`` (string)


  The ID of the Worker who possesses the Qualification to be revoked.

  

``--qualification-type-id`` (string)


  The ID of the Qualification type of the Qualification to be revoked.

  

``--reason`` (string)


  A text message that explains why the Qualification was revoked. The user who had the Qualification sees this message.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

