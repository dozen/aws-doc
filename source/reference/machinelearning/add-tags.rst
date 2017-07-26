[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning add-tags:


********
add-tags
********



===========
Description
===========



Adds one or more tags to an object, up to a limit of 10. Each tag consists of a key and an optional value. If you add a tag using a key that is already associated with the ML object, ``add-tags`` updates the tag's value.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/AddTags>`_


========
Synopsis
========

::

    add-tags
  --tags <value>
  --resource-id <value>
  --resource-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--tags`` (list)


  The key-value pairs to use to create tags. If you specify a key without specifying a value, Amazon ML creates a tag with the specified key and a value of null.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--resource-id`` (string)


  The ID of the ML object to tag. For example, ``exampleModelId`` .

  

``--resource-type`` (string)


  The type of the ML object to tag. 

  

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

  

  The ID of the ML object that was tagged.

  

  

ResourceType -> (string)

  

  The type of the ML object that was tagged.

  

  

