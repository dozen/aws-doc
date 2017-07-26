[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs delete-metric-filter:


********************
delete-metric-filter
********************



===========
Description
===========



Deletes a metric filter associated with the specified log group. 



========
Synopsis
========

::

    delete-metric-filter
  --log-group-name <value>
  --filter-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group that is associated with the metric filter to delete.

  

``--filter-name`` (string)


  The name of the metric filter to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None