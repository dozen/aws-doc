[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds delete-db-security-group:


************************
delete-db-security-group
************************



===========
Description
===========



Deletes a DB security group. 

 

.. note::

  The specified DB security group must not be associated with any DB instances.



========
Synopsis
========

::

    delete-db-security-group
  --db-security-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-security-group-name`` (string)


  The name of the DB security group to delete. 

   

  .. note::

    You cannot delete the default DB security group.

   

  Constraints: 

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   
  * Must not be "Default"
   
  * Cannot contain spaces
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None