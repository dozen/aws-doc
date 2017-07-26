[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk associate-qualification-with-worker:


***********************************
associate-qualification-with-worker
***********************************



===========
Description
===========



The ``associate-qualification-with-worker`` operation gives a Worker a Qualification. ``associate-qualification-with-worker`` does not require that the Worker submit a Qualification request. It gives the Qualification directly to the Worker. 

 

You can only assign a Qualification of a Qualification type that you created (using the ``create-qualification-type`` operation). 

 

.. note::

   

  Note: ``associate-qualification-with-worker`` does not affect any pending Qualification requests for the Qualification by the Worker. If you assign a Qualification to a Worker, then later grant a Qualification request made by the Worker, the granting of the request may modify the Qualification score. To resolve a pending Qualification request without affecting the Qualification the Worker already has, reject the request with the ``reject-qualification-request`` operation. 

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/AssociateQualificationWithWorker>`_


========
Synopsis
========

::

    associate-qualification-with-worker
  --qualification-type-id <value>
  --worker-id <value>
  [--integer-value <value>]
  [--send-notification | --no-send-notification]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--qualification-type-id`` (string)


  The ID of the Qualification type to use for the assigned Qualification.

  

``--worker-id`` (string)


  The ID of the Worker to whom the Qualification is being assigned. Worker IDs are included with submitted HIT assignments and Qualification requests. 

  

``--integer-value`` (integer)


  The value of the Qualification to assign.

  

``--send-notification`` | ``--no-send-notification`` (boolean)


  Specifies whether to send a notification email message to the Worker saying that the qualification was assigned to the Worker. Note: this is true by default. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

