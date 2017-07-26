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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/DeleteBatchPrediction>`_


========
Synopsis
========

::

    delete-batch-prediction
  --batch-prediction-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--batch-prediction-id`` (string)


  A user-supplied ID that uniquely identifies the ``BatchPrediction`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

BatchPredictionId -> (string)

  

  A user-supplied ID that uniquely identifies the ``BatchPrediction`` . This value should be identical to the value of the ``BatchPredictionID`` in the request.

  

  

