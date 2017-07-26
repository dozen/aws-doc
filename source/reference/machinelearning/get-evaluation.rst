[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning get-evaluation:


**************
get-evaluation
**************



===========
Description
===========



Returns an ``Evaluation`` that includes metadata as well as the current status of the ``Evaluation`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/GetEvaluation>`_


========
Synopsis
========

::

    get-evaluation
  --evaluation-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--evaluation-id`` (string)


  The ID of the ``Evaluation`` to retrieve. The evaluation of each ``MLModel`` is recorded and cataloged. The ID provides the means to access the information. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EvaluationId -> (string)

  

  The evaluation ID which is same as the ``EvaluationId`` in the request.

  

  

MLModelId -> (string)

  

  The ID of the ``MLModel`` that was the focus of the evaluation.

  

  

EvaluationDataSourceId -> (string)

  

  The ``DataSource`` used for this evaluation.

  

  

InputDataLocationS3 -> (string)

  

  The location of the data file or directory in Amazon Simple Storage Service (Amazon S3).

  

  

CreatedByIamUser -> (string)

  

  The AWS user account that invoked the evaluation. The account type can be either an AWS root account or an AWS Identity and Access Management (IAM) user account.

  

  

CreatedAt -> (timestamp)

  

  The time that the ``Evaluation`` was created. The time is expressed in epoch time.

  

  

LastUpdatedAt -> (timestamp)

  

  The time of the most recent edit to the ``Evaluation`` . The time is expressed in epoch time.

  

  

Name -> (string)

  

  A user-supplied name or description of the ``Evaluation`` . 

  

  

Status -> (string)

  

  The status of the evaluation. This element can have one of the following values:

   

   
  * ``PENDING`` - Amazon Machine Language (Amazon ML) submitted a request to evaluate an ``MLModel`` .
   
  * ``INPROGRESS`` - The evaluation is underway.
   
  * ``FAILED`` - The request to evaluate an ``MLModel`` did not run to completion. It is not usable.
   
  * ``COMPLETED`` - The evaluation process completed successfully.
   
  * ``DELETED`` - The ``Evaluation`` is marked as deleted. It is not usable.
   

  

  

PerformanceMetrics -> (structure)

  

  Measurements of how well the ``MLModel`` performed using observations referenced by the ``DataSource`` . One of the following metric is returned based on the type of the ``MLModel`` : 

   

   
  * BinaryAUC: A binary ``MLModel`` uses the Area Under the Curve (AUC) technique to measure performance.  
   
  * RegressionRMSE: A regression ``MLModel`` uses the Root Mean Square Error (RMSE) technique to measure performance. RMSE measures the difference between predicted and actual values for a single variable. 
   
  * MulticlassAvgFScore: A multiclass ``MLModel`` uses the F1 score technique to measure performance.  
   

   

  For more information about performance metrics, please see the `Amazon Machine Learning Developer Guide <http://docs.aws.amazon.com/machine-learning/latest/dg>`_ . 

  

  Properties -> (map)

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  

LogUri -> (string)

  

  A link to the file that contains logs of the ``create-evaluation`` operation.

  

  

Message -> (string)

  

  A description of the most recent details about evaluating the ``MLModel`` .

  

  

ComputeTime -> (long)

  

  The approximate CPU time in milliseconds that Amazon Machine Learning spent processing the ``Evaluation`` , normalized and scaled on computation resources. ``ComputeTime`` is only available if the ``Evaluation`` is in the ``COMPLETED`` state.

  

  

FinishedAt -> (timestamp)

  

  The epoch time when Amazon Machine Learning marked the ``Evaluation`` as ``COMPLETED`` or ``FAILED`` . ``FinishedAt`` is only available when the ``Evaluation`` is in the ``COMPLETED`` or ``FAILED`` state.

  

  

StartedAt -> (timestamp)

  

  The epoch time when Amazon Machine Learning marked the ``Evaluation`` as ``INPROGRESS`` . ``StartedAt`` isn't available if the ``Evaluation`` is in the ``PENDING`` state.

  

  

