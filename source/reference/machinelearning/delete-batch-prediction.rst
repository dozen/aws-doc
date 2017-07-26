[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning delete-batch-prediction:


***********************
delete-batch-prediction
***********************



===========
Description
===========



Assigns the DELETED status to a ``BatchPrediction`` , rendering it unusable.

 

After using the ``delete-batch-prediction`` operation, you can use the  get-batch-prediction operation to verify that the status of the ``BatchPrediction`` changed to DELETED.

 

**Caution:** The result of the ``delete-batch-prediction`` operation is irreversible.



========
Synopsis
========

::

    delete-batch-prediction
  --batch-prediction-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--batch-prediction-id`` (string)


  A user-supplied ID that uniquely identifies the ``BatchPrediction`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

BatchPredictionId -> (string)

  

  A user-supplied ID that uniquely identifies the ``BatchPrediction`` . This value should be identical to the value of the ``BatchPredictionID`` in the request.

  

  

