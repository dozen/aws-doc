[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk reject-assignment:


*****************
reject-assignment
*****************



===========
Description
===========



The ``reject-assignment`` operation rejects the results of a completed assignment. 

 

You can include an optional feedback message with the rejection, which the Worker can see in the Status section of the web site. When you include a feedback message with the rejection, it helps the Worker understand why the assignment was rejected, and can improve the quality of the results the Worker submits in the future. 

 

Only the Requester who created the HIT can reject an assignment for the HIT. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/RejectAssignment>`_


========
Synopsis
========

::

    reject-assignment
  --assignment-id <value>
  [--requester-feedback <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assignment-id`` (string)


  The ID of the assignment. The assignment must correspond to a HIT created by the Requester. 

  

``--requester-feedback`` (string)


  A message for the Worker, which the Worker can see in the Status section of the web site. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

