[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds delete-db-parameter-group:


*************************
delete-db-parameter-group
*************************



===========
Description
===========



Deletes a specified DBParameterGroup. The DBParameterGroup to be deleted cannot be associated with any DB instances. 



========
Synopsis
========

::

    delete-db-parameter-group
  --db-parameter-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-parameter-group-name`` (string)


  The name of the DB parameter group. 

   

  Constraints:

   

   
  * Must be the name of an existing DB parameter group
   
  * You cannot delete a default DB parameter group
   
  * Cannot be associated with any DB instances
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None