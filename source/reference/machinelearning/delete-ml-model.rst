[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning delete-ml-model:


***************
delete-ml-model
***************



===========
Description
===========



Assigns the ``DELETED`` status to an ``MLModel`` , rendering it unusable.

 

After using the ``delete-ml-model`` operation, you can use the ``get-ml-model`` operation to verify that the status of the ``MLModel`` changed to DELETED.

 

**Caution:** The result of the ``delete-ml-model`` operation is irreversible.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/DeleteMLModel>`_


========
Synopsis
========

::

    delete-ml-model
  --ml-model-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ml-model-id`` (string)


  A user-supplied ID that uniquely identifies the ``MLModel`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MLModelId -> (string)

  

  A user-supplied ID that uniquely identifies the ``MLModel`` . This value should be identical to the value of the ``MLModelID`` in the request.

  

  

