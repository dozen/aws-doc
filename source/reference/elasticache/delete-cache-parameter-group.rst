[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache delete-cache-parameter-group:


****************************
delete-cache-parameter-group
****************************



===========
Description
===========



The *delete-cache-parameter-group* action deletes the specified cache parameter group. You cannot delete a cache parameter group if it is associated with any cache clusters.



========
Synopsis
========

::

    delete-cache-parameter-group
  --cache-parameter-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-parameter-group-name`` (string)


  The name of the cache parameter group to delete.

   

  .. note::

    The specified cache security group must not be associated with any cache clusters.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None