[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning delete-data-source:


******************
delete-data-source
******************



===========
Description
===========



Assigns the DELETED status to a ``DataSource`` , rendering it unusable.

 

After using the ``delete-data-source`` operation, you can use the  get-data-source operation to verify that the status of the ``DataSource`` changed to DELETED.

 

**Caution:** The results of the ``delete-data-source`` operation are irreversible.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/DeleteDataSource>`_


========
Synopsis
========

::

    delete-data-source
  --data-source-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--data-source-id`` (string)


  A user-supplied ID that uniquely identifies the ``DataSource`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DataSourceId -> (string)

  

  A user-supplied ID that uniquely identifies the ``DataSource`` . This value should be identical to the value of the ``DataSourceID`` in the request.

  

  

