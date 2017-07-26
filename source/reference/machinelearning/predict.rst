[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning predict:


*******
predict
*******



===========
Description
===========



Generates a prediction for the observation using the specified ``ML Model`` .

 

.. note::

  Note 

  Not all response parameters will be populated. Whether a response parameter is populated depends on the type of model requested.

  



========
Synopsis
========

::

    predict
  --ml-model-id <value>
  --record <value>
  --predict-endpoint <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ml-model-id`` (string)


  A unique identifier of the ``MLModel`` .

  

``--record`` (map)


  A map of variable name-value pairs that represent an observation.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--predict-endpoint`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Prediction -> (structure)

  

  The output from a ``predict`` operation: 

   

   
  * ``Details`` - Contains the following attributes: DetailsAttributes.PREDICTIVE_MODEL_TYPE - REGRESSION | BINARY | MULTICLASS DetailsAttributes.ALGORITHM - SGD  
   
  * ``PredictedLabel`` - Present for either a BINARY or MULTICLASS ``MLModel`` request.  
   
  * ``PredictedScores`` - Contains the raw classification score corresponding to each label.  
   
  * ``PredictedValue`` - Present for a REGRESSION ``MLModel`` request.  
   

  

  predictedLabel -> (string)

    The prediction label for either a BINARY or MULTICLASS ``MLModel`` .

    

  predictedValue -> (float)

    The prediction value for REGRESSION ``MLModel`` .

    

  predictedScores -> (map)

    Provides the raw classification score corresponding to each label.

    key -> (string)

      

      

    value -> (float)

      

      

    

  details -> (map)

    Provides any additional details regarding the prediction.

    key -> (string)

      Contains the key values of ``DetailsMap`` : PredictiveModelType - Indicates the type of the ``MLModel`` . Algorithm - Indicates the algorithm was used for the ``MLModel`` .

      

    value -> (string)

      

      

    

  

