[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning get-batch-prediction:


********************
get-batch-prediction
********************



===========
Description
===========



Returns a ``BatchPrediction`` that includes detailed metadata, status, and data file information for a ``Batch Prediction`` request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/GetBatchPrediction>`_


========
Synopsis
========

::

    get-batch-prediction
  --batch-prediction-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--batch-prediction-id`` (string)


  An ID assigned to the ``BatchPrediction`` at creation.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

BatchPredictionId -> (string)

  

  An ID assigned to the ``BatchPrediction`` at creation. This value should be identical to the value of the ``BatchPredictionID`` in the request.

  

  

MLModelId -> (string)

  

  The ID of the ``MLModel`` that generated predictions for the ``BatchPrediction`` request.

  

  

BatchPredictionDataSourceId -> (string)

  

  The ID of the ``DataSource`` that was used to create the ``BatchPrediction`` . 

  

  

InputDataLocationS3 -> (string)

  

  The location of the data file or directory in Amazon Simple Storage Service (Amazon S3).

  

  

CreatedByIamUser -> (string)

  

  The AWS user account that invoked the ``BatchPrediction`` . The account type can be either an AWS root account or an AWS Identity and Access Management (IAM) user account.

  

  

CreatedAt -> (timestamp)

  

  The time when the ``BatchPrediction`` was created. The time is expressed in epoch time.

  

  

LastUpdatedAt -> (timestamp)

  

  The time of the most recent edit to ``BatchPrediction`` . The time is expressed in epoch time.

  

  

Name -> (string)

  

  A user-supplied name or description of the ``BatchPrediction`` .

  

  

Status -> (string)

  

  The status of the ``BatchPrediction`` , which can be one of the following values:

   

   
  * ``PENDING`` - Amazon Machine Learning (Amazon ML) submitted a request to generate batch predictions.
   
  * ``INPROGRESS`` - The batch predictions are in progress.
   
  * ``FAILED`` - The request to perform a batch prediction did not run to completion. It is not usable.
   
  * ``COMPLETED`` - The batch prediction process completed successfully.
   
  * ``DELETED`` - The ``BatchPrediction`` is marked as deleted. It is not usable.
   

  

  

OutputUri -> (string)

  

  The location of an Amazon S3 bucket or directory to receive the operation results.

  

  

LogUri -> (string)

  

  A link to the file that contains logs of the ``create-batch-prediction`` operation.

  

  

Message -> (string)

  

  A description of the most recent details about processing the batch prediction request.

  

  

ComputeTime -> (long)

  

  The approximate CPU time in milliseconds that Amazon Machine Learning spent processing the ``BatchPrediction`` , normalized and scaled on computation resources. ``ComputeTime`` is only available if the ``BatchPrediction`` is in the ``COMPLETED`` state.

  

  

FinishedAt -> (timestamp)

  

  The epoch time when Amazon Machine Learning marked the ``BatchPrediction`` as ``COMPLETED`` or ``FAILED`` . ``FinishedAt`` is only available when the ``BatchPrediction`` is in the ``COMPLETED`` or ``FAILED`` state.

  

  

StartedAt -> (timestamp)

  

  The epoch time when Amazon Machine Learning marked the ``BatchPrediction`` as ``INPROGRESS`` . ``StartedAt`` isn't available if the ``BatchPrediction`` is in the ``PENDING`` state.

  

  

TotalRecordCount -> (long)

  

  The number of total records that Amazon Machine Learning saw while processing the ``BatchPrediction`` .

  

  

InvalidRecordCount -> (long)

  

  The number of invalid records that Amazon Machine Learning saw while processing the ``BatchPrediction`` .

  

  

