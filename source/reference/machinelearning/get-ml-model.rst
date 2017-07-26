[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning get-ml-model:


************
get-ml-model
************



===========
Description
===========



Returns an ``MLModel`` that includes detailed metadata, data source information, and the current status of the ``MLModel`` .

 

``get-ml-model`` provides results in normal or verbose format. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/GetMLModel>`_


========
Synopsis
========

::

    get-ml-model
  --ml-model-id <value>
  [--verbose | --no-verbose]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ml-model-id`` (string)


  The ID assigned to the ``MLModel`` at creation.

  

``--verbose`` | ``--no-verbose`` (boolean)


  Specifies whether the ``get-ml-model`` operation should return ``Recipe`` .

   

  If true, ``Recipe`` is returned.

   

  If false, ``Recipe`` is not returned.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MLModelId -> (string)

  

  The MLModel ID,which is same as the ``MLModelId`` in the request.

  

  

TrainingDataSourceId -> (string)

  

  The ID of the training ``DataSource`` .

  

  

CreatedByIamUser -> (string)

  

  The AWS user account from which the ``MLModel`` was created. The account type can be either an AWS root account or an AWS Identity and Access Management (IAM) user account.

  

  

CreatedAt -> (timestamp)

  

  The time that the ``MLModel`` was created. The time is expressed in epoch time.

  

  

LastUpdatedAt -> (timestamp)

  

  The time of the most recent edit to the ``MLModel`` . The time is expressed in epoch time.

  

  

Name -> (string)

  

  A user-supplied name or description of the ``MLModel`` .

  

  

Status -> (string)

  

  The current status of the ``MLModel`` . This element can have one of the following values:

   

   
  * ``PENDING`` - Amazon Machine Learning (Amazon ML) submitted a request to describe a ``MLModel`` .
   
  * ``INPROGRESS`` - The request is processing.
   
  * ``FAILED`` - The request did not run to completion. The ML model isn't usable.
   
  * ``COMPLETED`` - The request completed successfully.
   
  * ``DELETED`` - The ``MLModel`` is marked as deleted. It isn't usable.
   

  

  

SizeInBytes -> (long)

  

  Long integer type that is a 64-bit signed number.

  

  

EndpointInfo -> (structure)

  

  The current endpoint of the ``MLModel`` 

  

  PeakRequestsPerSecond -> (integer)

    

    The maximum processing rate for the real-time endpoint for ``MLModel`` , measured in incoming requests per second.

    

    

  CreatedAt -> (timestamp)

    

    The time that the request to create the real-time endpoint for the ``MLModel`` was received. The time is expressed in epoch time.

    

    

  EndpointUrl -> (string)

    

    The URI that specifies where to send real-time prediction requests for the ``MLModel`` .

     

    .. note::

      Note 

      The application must wait until the real-time endpoint is ready before using this URI.

       

    

    

  EndpointStatus -> (string)

    

    The current status of the real-time endpoint for the ``MLModel`` . This element can have one of the following values: 

     

     
    * ``NONE`` - Endpoint does not exist or was previously deleted.
     
    * ``READY`` - Endpoint is ready to be used for real-time predictions.
     
    * ``UPDATING`` - Updating/creating the endpoint. 
     

    

    

  

TrainingParameters -> (map)

  

  A list of the training parameters in the ``MLModel`` . The list is implemented as a map of key-value pairs.

   

  The following is the current set of training parameters: 

   

   
  * ``sgd.maxMLModelSizeInBytes`` - The maximum allowed size of the model. Depending on the input data, the size of the model might affect its performance. The value is an integer that ranges from ``100000`` to ``2147483648`` . The default value is ``33554432`` . 
   
  * ``sgd.maxPasses`` - The number of times that the training process traverses the observations to build the ``MLModel`` . The value is an integer that ranges from ``1`` to ``10000`` . The default value is ``10`` .
   
  * ``sgd.shuffleType`` - Whether Amazon ML shuffles the training data. Shuffling data improves a model's ability to find the optimal solution for a variety of data types. The valid values are ``auto`` and ``none`` . The default value is ``none`` . We strongly recommend that you shuffle your data.
   
  * ``sgd.l1RegularizationAmount`` - The coefficient regularization L1 norm. It controls overfitting the data by penalizing large coefficients. This tends to drive coefficients to zero, resulting in a sparse feature set. If you use this parameter, start by specifying a small value, such as ``1.0E-08`` . The value is a double that ranges from ``0`` to ``MAX_DOUBLE`` . The default is to not use L1 normalization. This parameter can't be used when ``L2`` is specified. Use this parameter sparingly. 
   
  * ``sgd.l2RegularizationAmount`` - The coefficient regularization L2 norm. It controls overfitting the data by penalizing large coefficients. This tends to drive coefficients to small, nonzero values. If you use this parameter, start by specifying a small value, such as ``1.0E-08`` . The value is a double that ranges from ``0`` to ``MAX_DOUBLE`` . The default is to not use L2 normalization. This parameter can't be used when ``L1`` is specified. Use this parameter sparingly. 
   

  

  key -> (string)

    

    String type.

    

    

  value -> (string)

    

    String type.

    

    

  

InputDataLocationS3 -> (string)

  

  The location of the data file or directory in Amazon Simple Storage Service (Amazon S3).

  

  

MLModelType -> (string)

  

  Identifies the ``MLModel`` category. The following are the available types: 

   

   
  * REGRESSION -- Produces a numeric result. For example, "What price should a house be listed at?"
   
  * BINARY -- Produces one of two possible results. For example, "Is this an e-commerce website?"
   
  * MULTICLASS -- Produces one of several possible results. For example, "Is this a HIGH, LOW or MEDIUM risk trade?"
   

  

  

ScoreThreshold -> (float)

  

  The scoring threshold is used in binary classification ``MLModel``  models. It marks the boundary between a positive prediction and a negative prediction.

   

  Output values greater than or equal to the threshold receive a positive result from the MLModel, such as ``true`` . Output values less than the threshold receive a negative response from the MLModel, such as ``false`` .

  

  

ScoreThresholdLastUpdatedAt -> (timestamp)

  

  The time of the most recent edit to the ``ScoreThreshold`` . The time is expressed in epoch time.

  

  

LogUri -> (string)

  

  A link to the file that contains logs of the ``create-ml-model`` operation.

  

  

Message -> (string)

  

  A description of the most recent details about accessing the ``MLModel`` .

  

  

ComputeTime -> (long)

  

  The approximate CPU time in milliseconds that Amazon Machine Learning spent processing the ``MLModel`` , normalized and scaled on computation resources. ``ComputeTime`` is only available if the ``MLModel`` is in the ``COMPLETED`` state.

  

  

FinishedAt -> (timestamp)

  

  The epoch time when Amazon Machine Learning marked the ``MLModel`` as ``COMPLETED`` or ``FAILED`` . ``FinishedAt`` is only available when the ``MLModel`` is in the ``COMPLETED`` or ``FAILED`` state.

  

  

StartedAt -> (timestamp)

  

  The epoch time when Amazon Machine Learning marked the ``MLModel`` as ``INPROGRESS`` . ``StartedAt`` isn't available if the ``MLModel`` is in the ``PENDING`` state.

  

  

Recipe -> (string)

  

  The recipe to use when training the ``MLModel`` . The ``Recipe`` provides detailed information about the observation data to use during training, and manipulations to perform on the observation data during training.

   

  .. note::

    Note 

    This parameter is provided as part of the verbose format.

    

  

  

Schema -> (string)

  

  The schema used by all of the data files referenced by the ``DataSource`` .

   

  .. note::

    Note 

    This parameter is provided as part of the verbose format.

    

  

  

