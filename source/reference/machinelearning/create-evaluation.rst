[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning create-evaluation:


*****************
create-evaluation
*****************



===========
Description
===========



Creates a new ``Evaluation`` of an ``MLModel`` . An ``MLModel`` is evaluated on a set of observations associated to a ``DataSource`` . Like a ``DataSource`` for an ``MLModel`` , the ``DataSource`` for an ``Evaluation`` contains values for the Target Variable. The ``Evaluation`` compares the predicted result for each observation to the actual outcome and provides a summary so that you know how effective the ``MLModel`` functions on the test data. Evaluation generates a relevant performance metric such as BinaryAUC, RegressionRMSE or MulticlassAvgFScore based on the corresponding ``MLModelType`` : ``BINARY`` , ``REGRESSION`` or ``MULTICLASS`` . 

 

``create-evaluation`` is an asynchronous operation. In response to ``create-evaluation`` , Amazon Machine Learning (Amazon ML) immediately returns and sets the evaluation status to ``PENDING`` . After the ``Evaluation`` is created and ready for use, Amazon ML sets the status to ``COMPLETED`` . 

 

You can use the  get-evaluation operation to check progress of the evaluation during the creation operation.



========
Synopsis
========

::

    create-evaluation
  --evaluation-id <value>
  [--evaluation-name <value>]
  --ml-model-id <value>
  --evaluation-data-source-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--evaluation-id`` (string)


  A user-supplied ID that uniquely identifies the ``Evaluation`` .

  

``--evaluation-name`` (string)


  A user-supplied name or description of the ``Evaluation`` .

  

``--ml-model-id`` (string)


  The ID of the ``MLModel`` to evaluate.

   

  The schema used in creating the ``MLModel`` must match the schema of the ``DataSource`` used in the ``Evaluation`` .

  

``--evaluation-data-source-id`` (string)


  The ID of the ``DataSource`` for the evaluation. The schema of the ``DataSource`` must match the schema used to create the ``MLModel`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

EvaluationId -> (string)

  

  The user-supplied ID that uniquely identifies the ``Evaluation`` . This value should be identical to the value of the ``EvaluationId`` in the request.

  

  

