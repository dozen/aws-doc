[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning update-data-source:


******************
update-data-source
******************



===========
Description
===========



Updates the ``DataSourceName`` of a ``DataSource`` .

 

You can use the  get-data-source operation to view the contents of the updated data element.



========
Synopsis
========

::

    update-data-source
  --data-source-id <value>
  --data-source-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--data-source-id`` (string)


  The ID assigned to the ``DataSource`` during creation.

  

``--data-source-name`` (string)


  A new user-supplied name or description of the ``DataSource`` that will replace the current description. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DataSourceId -> (string)

  

  The ID assigned to the ``DataSource`` during creation. This value should be identical to the value of the ``DataSourceID`` in the request.

  

  

