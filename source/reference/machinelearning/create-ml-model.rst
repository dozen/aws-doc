[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning create-ml-model:


***************
create-ml-model
***************



===========
Description
===========



Creates a new ``MLModel`` using the data files and the recipe as information sources. 

 

An ``MLModel`` is nearly immutable. Users can only update the ``MLModelName`` and the ``ScoreThreshold`` in an ``MLModel`` without creating a new ``MLModel`` . 

 

``create-ml-model`` is an asynchronous operation. In response to ``create-ml-model`` , Amazon Machine Learning (Amazon ML) immediately returns and sets the ``MLModel`` status to ``PENDING`` . After the ``MLModel`` is created and ready for use, Amazon ML sets the status to ``COMPLETED`` . 

 

You can use the  get-ml-model operation to check progress of the ``MLModel`` during the creation operation.

 

  create-ml-model requires a ``DataSource`` with computed statistics, which can be created by setting ``ComputeStatistics`` to ``true`` in  create-data-source-from-rds ,  create-data-source-from-s3 , or  create-data-source-from-redshift operations. 



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
  [--generate-cli-skeleton]




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
   

   

  For more information, see the `Amazon Machine Learning Developer Guide`_ .

  

  Possible values:

  
  *   ``REGRESSION``

  
  *   ``BINARY``

  
  *   ``MULTICLASS``

  

  

``--parameters`` (map)


  A list of the training parameters in the ``MLModel`` . The list is implemented as a map of key/value pairs.

   

  The following is the current set of training parameters: 

   

   
  * ``sgd.l1RegularizationAmount`` - Coefficient regularization L1 norm. It controls overfitting the data by penalizing large coefficients. This tends to drive coefficients to zero, resulting in sparse feature set. If you use this parameter, start by specifying a small value such as 1.0E-08. The value is a double that ranges from 0 to MAX_DOUBLE. The default is not to use L1 normalization. The parameter cannot be used when ``L2`` is specified. Use this parameter sparingly. 
   
  * ``sgd.l2RegularizationAmount`` - Coefficient regularization L2 norm. It controls overfitting the data by penalizing large coefficients. This tends to drive coefficients to small, nonzero values. If you use this parameter, start by specifying a small value such as 1.0E-08. The valuseis a double that ranges from 0 to MAX_DOUBLE. The default is not to use L2 normalization. This cannot be used when ``L1`` is specified. Use this parameter sparingly. 
   
  * ``sgd.maxPasses`` - Number of times that the training process traverses the observations to build the ``MLModel`` . The value is an integer that ranges from 1 to 10000. The default value is 10. 
   
  * ``sgd.maxMLModelSizeInBytes`` - Maximum allowed size of the model. Depending on the input data, the size of the model might affect its performance. The value is an integer that ranges from 100000 to 2147483648. The default value is 33554432.  
   

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--training-data-source-id`` (string)


  The ``DataSource`` that points to the training data.

  

``--recipe`` (string)


  The data recipe for creating ``MLModel`` . You must specify either the recipe or its URI. If you don’t specify a recipe or its URI, Amazon ML creates a default.

  

``--recipe-uri`` (string)


  The Amazon Simple Storage Service (Amazon S3) location and file name that contains the ``MLModel`` recipe. You must specify either the recipe or its URI. If you don’t specify a recipe or its URI, Amazon ML creates a default.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

MLModelId -> (string)

  

  A user-supplied ID that uniquely identifies the ``MLModel`` . This value should be identical to the value of the ``MLModelId`` in the request. 

  

  



.. _Amazon Machine Learning Developer Guide: http://docs.aws.amazon.com/machine-learning/latest/dg
