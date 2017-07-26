[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning create-batch-prediction:


***********************
create-batch-prediction
***********************



===========
Description
===========



Generates predictions for a group of observations. The observations to process exist in one or more data files referenced by a ``DataSource`` . This operation creates a new ``BatchPrediction`` , and uses an ``MLModel`` and the data files referenced by the ``DataSource`` as information sources. 

 

``create-batch-prediction`` is an asynchronous operation. In response to ``create-batch-prediction`` , Amazon Machine Learning (Amazon ML) immediately returns and sets the ``BatchPrediction`` status to ``PENDING`` . After the ``BatchPrediction`` completes, Amazon ML sets the status to ``COMPLETED`` . 

 

You can poll for status updates by using the  get-batch-prediction operation and checking the ``Status`` parameter of the result. After the ``COMPLETED`` status appears, the results are available in the location specified by the ``OutputUri`` parameter.



========
Synopsis
========

::

    create-batch-prediction
  --batch-prediction-id <value>
  [--batch-prediction-name <value>]
  --ml-model-id <value>
  --batch-prediction-data-source-id <value>
  --output-uri <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--batch-prediction-id`` (string)


  A user-supplied ID that uniquely identifies the ``BatchPrediction`` .

  

``--batch-prediction-name`` (string)


  A user-supplied name or description of the ``BatchPrediction`` . ``BatchPredictionName`` can only use the UTF-8 character set.

  

``--ml-model-id`` (string)


  The ID of the ``MLModel`` that will generate predictions for the group of observations. 

  

``--batch-prediction-data-source-id`` (string)


  The ID of the ``DataSource`` that points to the group of observations to predict.

  

``--output-uri`` (string)


  The location of an Amazon Simple Storage Service (Amazon S3) bucket or directory to store the batch prediction results. The following substrings are not allowed in the s3 key portion of the "outputURI" field: ':', '//', '/./', '/../'.

   

  Amazon ML needs permissions to store and retrieve the logs on your behalf. For information about how to set permissions, see the `Amazon Machine Learning Developer Guide`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

BatchPredictionId -> (string)

  

  A user-supplied ID that uniquely identifies the ``BatchPrediction`` . This value is identical to the value of the ``BatchPredictionId`` in the request.

  

  



.. _Amazon Machine Learning Developer Guide: http://docs.aws.amazon.com/machine-learning/latest/dg
