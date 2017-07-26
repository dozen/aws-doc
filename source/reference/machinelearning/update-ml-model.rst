[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning update-ml-model:


***************
update-ml-model
***************



===========
Description
===========



Updates the ``MLModelName`` and the ``score-threshold`` of an ``MLModel`` .

 

You can use the  get-ml-model operation to view the contents of the updated data element.



========
Synopsis
========

::

    update-ml-model
  --ml-model-id <value>
  [--ml-model-name <value>]
  [--score-threshold <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ml-model-id`` (string)


  The ID assigned to the ``MLModel`` during creation.

  

``--ml-model-name`` (string)


  A user-supplied name or description of the ``MLModel`` .

  

``--score-threshold`` (float)


  The ``score-threshold`` used in binary classification ``MLModel`` that marks the boundary between a positive prediction and a negative prediction.

   

  Output values greater than or equal to the ``score-threshold`` receive a positive result from the ``MLModel`` , such as ``true`` . Output values less than the ``score-threshold`` receive a negative response from the ``MLModel`` , such as ``false`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

MLModelId -> (string)

  

  The ID assigned to the ``MLModel`` during creation. This value should be identical to the value of the ``MLModelID`` in the request.

  

  

