[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds delete-db-cluster-parameter-group:


*********************************
delete-db-cluster-parameter-group
*********************************



===========
Description
===========



Deletes a specified DB cluster parameter group. The DB cluster parameter group to be deleted cannot be associated with any DB clusters. 

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    delete-db-cluster-parameter-group
  --db-cluster-parameter-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-cluster-parameter-group-name`` (string)


  The name of the DB cluster parameter group. 

   

  Constraints:

   

   
  * Must be the name of an existing DB cluster parameter group.
   
  * You cannot delete a default DB cluster parameter group.
   
  * Cannot be associated with any DB clusters.
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Aurora on Amazon RDS: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html
