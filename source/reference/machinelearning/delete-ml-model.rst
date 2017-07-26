[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning delete-ml-model:


***************
delete-ml-model
***************



===========
Description
===========



Assigns the DELETED status to an ``MLModel`` , rendering it unusable.

 

After using the ``delete-ml-model`` operation, you can use the  get-ml-model operation to verify that the status of the ``MLModel`` changed to DELETED.

 

**Caution:** The result of the ``delete-ml-model`` operation is irreversible.



========
Synopsis
========

::

    delete-ml-model
  --ml-model-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ml-model-id`` (string)


  A user-supplied ID that uniquely identifies the ``MLModel`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

MLModelId -> (string)

  

  A user-supplied ID that uniquely identifies the ``MLModel`` . This value should be identical to the value of the ``MLModelID`` in the request.

  

  

