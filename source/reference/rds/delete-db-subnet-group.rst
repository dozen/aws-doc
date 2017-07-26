[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds delete-db-subnet-group:


**********************
delete-db-subnet-group
**********************



===========
Description
===========



Deletes a DB subnet group. 

 

.. note::

  The specified database subnet group must not be associated with any DB instances.



========
Synopsis
========

::

    delete-db-subnet-group
  --db-subnet-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-subnet-group-name`` (string)


  The name of the database subnet group to delete. 

   

  .. note::

    You cannot delete the default subnet group.

   

  Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

   

  Example: ``mySubnetgroup`` 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None