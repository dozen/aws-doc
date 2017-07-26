[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning update-ml-model:


***************
update-ml-model
***************



===========
Description
===========



Updates the ``MLModelName`` and the ``score-threshold`` of an ``MLModel`` .

 

You can use the ``get-ml-model`` operation to view the contents of the updated data element.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/UpdateMLModel>`_


========
Synopsis
========

::

    update-ml-model
  --ml-model-id <value>
  [--ml-model-name <value>]
  [--score-threshold <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ml-model-id`` (string)


  The ID assigned to the ``MLModel`` during creation.

  

``--ml-model-name`` (string)


  A user-supplied name or description of the ``MLModel`` .

  

``--score-threshold`` (float)


  The ``score-threshold`` used in binary classification ``MLModel`` that marks the boundary between a positive prediction and a negative prediction.

   

  Output values greater than or equal to the ``score-threshold`` receive a positive result from the ``MLModel`` , such as ``true`` . Output values less than the ``score-threshold`` receive a negative response from the ``MLModel`` , such as ``false`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MLModelId -> (string)

  

  The ID assigned to the ``MLModel`` during creation. This value should be identical to the value of the ``MLModelID`` in the request.

  

  

