[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning update-evaluation:


*****************
update-evaluation
*****************



===========
Description
===========



Updates the ``EvaluationName`` of an ``Evaluation`` .

 

You can use the  get-evaluation operation to view the contents of the updated data element.



========
Synopsis
========

::

    update-evaluation
  --evaluation-id <value>
  --evaluation-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--evaluation-id`` (string)


  The ID assigned to the ``Evaluation`` during creation.

  

``--evaluation-name`` (string)


  A new user-supplied name or description of the ``Evaluation`` that will replace the current content. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

EvaluationId -> (string)

  

  The ID assigned to the ``Evaluation`` during creation. This value should be identical to the value of the ``Evaluation`` in the request.

  

  

