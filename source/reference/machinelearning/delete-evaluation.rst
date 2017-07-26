[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning delete-evaluation:


*****************
delete-evaluation
*****************



===========
Description
===========



Assigns the ``DELETED`` status to an ``Evaluation`` , rendering it unusable.

 

After invoking the ``delete-evaluation`` operation, you can use the  get-evaluation operation to verify that the status of the ``Evaluation`` changed to ``DELETED`` .

 

**Caution:** The results of the ``delete-evaluation`` operation are irreversible.



========
Synopsis
========

::

    delete-evaluation
  --evaluation-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--evaluation-id`` (string)


  A user-supplied ID that uniquely identifies the ``Evaluation`` to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

EvaluationId -> (string)

  

  A user-supplied ID that uniquely identifies the ``Evaluation`` . This value should be identical to the value of the ``EvaluationId`` in the request.

  

  

