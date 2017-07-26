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

  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/Predict>`_


========
Synopsis
========

::

    predict
  --ml-model-id <value>
  --record <value>
  --predict-endpoint <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Prediction -> (structure)

  

  The output from a ``predict`` operation: 

   

   
  * ``Details`` - Contains the following attributes: ``DetailsAttributes.PREDICTIVE_MODEL_TYPE - REGRESSION | BINARY | MULTICLASS``  ``DetailsAttributes.ALGORITHM - SGD``   
   
  * ``PredictedLabel`` - Present for either a ``BINARY`` or ``MULTICLASS``  ``MLModel`` request.  
   
  * ``PredictedScores`` - Contains the raw classification score corresponding to each label.  
   
  * ``PredictedValue`` - Present for a ``REGRESSION``  ``MLModel`` request.  
   

  

  predictedLabel -> (string)

    

    The prediction label for either a ``BINARY`` or ``MULTICLASS``  ``MLModel`` .

    

    

  predictedValue -> (float)

    The prediction value for ``REGRESSION``  ``MLModel`` .

    

  predictedScores -> (map)

    Provides the raw classification score corresponding to each label.

    key -> (string)

      

      

    value -> (float)

      

      

    

  details -> (map)

    Provides any additional details regarding the prediction.

    key -> (string)

      Contains the key values of ``DetailsMap`` : ``PredictiveModelType`` - Indicates the type of the ``MLModel`` . ``Algorithm`` - Indicates the algorithm that was used for the ``MLModel`` .

      

    value -> (string)

      

      

    

  

