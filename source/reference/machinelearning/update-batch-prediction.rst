[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning update-batch-prediction:


***********************
update-batch-prediction
***********************



===========
Description
===========



Updates the ``BatchPredictionName`` of a ``BatchPrediction`` .

 

You can use the  get-batch-prediction operation to view the contents of the updated data element.



========
Synopsis
========

::

    update-batch-prediction
  --batch-prediction-id <value>
  --batch-prediction-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--batch-prediction-id`` (string)


  The ID assigned to the ``BatchPrediction`` during creation.

  

``--batch-prediction-name`` (string)


  A new user-supplied name or description of the ``BatchPrediction`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

BatchPredictionId -> (string)

  

  The ID assigned to the ``BatchPrediction`` during creation. This value should be identical to the value of the ``BatchPredictionId`` in the request.

  

  

