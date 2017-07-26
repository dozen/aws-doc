[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning create-ml-model:


***************
create-ml-model
***************



===========
Description
===========



Creates a new ``MLModel`` using the ``DataSource`` and the recipe as information sources. 

 

An ``MLModel`` is nearly immutable. Users can update only the ``MLModelName`` and the ``ScoreThreshold`` in an ``MLModel`` without creating a new ``MLModel`` . 

 

``create-ml-model`` is an asynchronous operation. In response to ``create-ml-model`` , Amazon Machine Learning (Amazon ML) immediately returns and sets the ``MLModel`` status to ``PENDING`` . After the ``MLModel`` has been created and ready is for use, Amazon ML sets the status to ``COMPLETED`` . 

 

You can use the ``get-ml-model`` operation to check the progress of the ``MLModel`` during the creation operation.

 

 ``create-ml-model`` requires a ``DataSource`` with computed statistics, which can be created by setting ``ComputeStatistics`` to ``true`` in ``create-data-source-from-rds`` , ``create-data-source-from-s3`` , or ``create-data-source-from-redshift`` operations. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/CreateMLModel>`_


========
Synopsis
========

::

    create-ml-model
  --ml-model-id <value>
  [--ml-model-name <value>]
  --ml-model-type <value>
  [--parameters <value>]
  --training-data-source-id <value>
  [--recipe <value>]
  [--recipe-uri <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ml-model-id`` (string)


  A user-supplied ID that uniquely identifies the ``MLModel`` .

  

``--ml-model-name`` (string)


  A user-supplied name or description of the ``MLModel`` .

  

``--ml-model-type`` (string)


  The category of supervised learning that this ``MLModel`` will address. Choose from the following types:

   

   
  * Choose ``REGRESSION`` if the ``MLModel`` will be used to predict a numeric value.
   
  * Choose ``BINARY`` if the ``MLModel`` result has two possible values.
   
  * Choose ``MULTICLASS`` if the ``MLModel`` result has a limited number of values. 
   

   

  For more information, see the `Amazon Machine Learning Developer Guide <http://docs.aws.amazon.com/machine-learning/latest/dg>`_ .

  

  Possible values:

  
  *   ``REGRESSION``

  
  *   ``BINARY``

  
  *   ``MULTICLASS``

  

  

``--parameters`` (map)


  A list of the training parameters in the ``MLModel`` . The list is implemented as a map of key-value pairs.

   

  The following is the current set of training parameters: 

   

   
  * ``sgd.maxMLModelSizeInBytes`` - The maximum allowed size of the model. Depending on the input data, the size of the model might affect its performance. The value is an integer that ranges from ``100000`` to ``2147483648`` . The default value is ``33554432`` . 
   
  * ``sgd.maxPasses`` - The number of times that the training process traverses the observations to build the ``MLModel`` . The value is an integer that ranges from ``1`` to ``10000`` . The default value is ``10`` .
   
  * ``sgd.shuffleType`` - Whether Amazon ML shuffles the training data. Shuffling the data improves a model's ability to find the optimal solution for a variety of data types. The valid values are ``auto`` and ``none`` . The default value is ``none`` . We strongly recommend that you shuffle your data. 
   
  * ``sgd.l1RegularizationAmount`` - The coefficient regularization L1 norm. It controls overfitting the data by penalizing large coefficients. This tends to drive coefficients to zero, resulting in a sparse feature set. If you use this parameter, start by specifying a small value, such as ``1.0E-08`` . The value is a double that ranges from ``0`` to ``MAX_DOUBLE`` . The default is to not use L1 normalization. This parameter can't be used when ``L2`` is specified. Use this parameter sparingly. 
   
  * ``sgd.l2RegularizationAmount`` - The coefficient regularization L2 norm. It controls overfitting the data by penalizing large coefficients. This tends to drive coefficients to small, nonzero values. If you use this parameter, start by specifying a small value, such as ``1.0E-08`` . The value is a double that ranges from ``0`` to ``MAX_DOUBLE`` . The default is to not use L2 normalization. This parameter can't be used when ``L1`` is specified. Use this parameter sparingly. 
   

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--training-data-source-id`` (string)


  The ``DataSource`` that points to the training data.

  

``--recipe`` (string)


  The data recipe for creating the ``MLModel`` . You must specify either the recipe or its URI. If you don't specify a recipe or its URI, Amazon ML creates a default.

  

``--recipe-uri`` (string)


  The Amazon Simple Storage Service (Amazon S3) location and file name that contains the ``MLModel`` recipe. You must specify either the recipe or its URI. If you don't specify a recipe or its URI, Amazon ML creates a default.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MLModelId -> (string)

  

  A user-supplied ID that uniquely identifies the ``MLModel`` . This value should be identical to the value of the ``MLModelId`` in the request. 

  

  

