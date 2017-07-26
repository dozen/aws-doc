[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning describe-tags:


*************
describe-tags
*************



===========
Description
===========



Describes one or more of the tags for your Amazon ML object.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/DescribeTags>`_


========
Synopsis
========

::

    describe-tags
  --resource-id <value>
  --resource-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-id`` (string)


  The ID of the ML object. For example, ``exampleModelId`` . 

  

``--resource-type`` (string)


  The type of the ML object.

  

  Possible values:

  
  *   ``BatchPrediction``

  
  *   ``DataSource``

  
  *   ``Evaluation``

  
  *   ``MLModel``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ResourceId -> (string)

  

  The ID of the tagged ML object.

  

  

ResourceType -> (string)

  

  The type of the tagged ML object.

  

  

Tags -> (list)

  

  A list of tags associated with the ML object.

  

  (structure)

    

    A custom key-value pair associated with an ML object, such as an ML model.

    

    Key -> (string)

      

      A unique identifier for the tag. Valid characters include Unicode letters, digits, white space, _, ., /, =, +, -, %, and @.

      

      

    Value -> (string)

      

      An optional string, typically used to describe or define the tag. Valid characters include Unicode letters, digits, white space, _, ., /, =, +, -, %, and @.

      

      

    

  

