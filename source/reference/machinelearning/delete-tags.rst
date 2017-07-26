[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning delete-tags:


***********
delete-tags
***********



===========
Description
===========



Deletes the specified tags associated with an ML object. After this operation is complete, you can't recover deleted tags.

 

If you specify a tag that doesn't exist, Amazon ML ignores it.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/DeleteTags>`_


========
Synopsis
========

::

    delete-tags
  --tag-keys <value>
  --resource-id <value>
  --resource-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--tag-keys`` (list)


  One or more tags to delete.

  



Syntax::

  "string" "string" ...



``--resource-id`` (string)


  The ID of the tagged ML object. For example, ``exampleModelId`` .

  

``--resource-type`` (string)


  The type of the tagged ML object.

  

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

  

  The ID of the ML object from which tags were deleted.

  

  

ResourceType -> (string)

  

  The type of the ML object from which tags were deleted.

  

  

