[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache delete-cache-subnet-group:


*************************
delete-cache-subnet-group
*************************



===========
Description
===========



The *delete-cache-subnet-group* action deletes a cache subnet group.

 

.. note::

  You cannot delete a cache subnet group if it is associated with any cache clusters.



========
Synopsis
========

::

    delete-cache-subnet-group
  --cache-subnet-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-subnet-group-name`` (string)


  The name of the cache subnet group to delete.

   

  Constraints: Must contain no more than 255 alphanumeric characters or hyphens.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None