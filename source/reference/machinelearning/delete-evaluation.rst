[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning delete-evaluation:


*****************
delete-evaluation
*****************



===========
Description
===========



Assigns the ``DELETED`` status to an ``Evaluation`` , rendering it unusable.

 

After invoking the ``delete-evaluation`` operation, you can use the ``get-evaluation`` operation to verify that the status of the ``Evaluation`` changed to ``DELETED`` .

 Caution 

The results of the ``delete-evaluation`` operation are irreversible.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/DeleteEvaluation>`_


========
Synopsis
========

::

    delete-evaluation
  --evaluation-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--evaluation-id`` (string)


  A user-supplied ID that uniquely identifies the ``Evaluation`` to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EvaluationId -> (string)

  

  A user-supplied ID that uniquely identifies the ``Evaluation`` . This value should be identical to the value of the ``EvaluationId`` in the request.

  

  

