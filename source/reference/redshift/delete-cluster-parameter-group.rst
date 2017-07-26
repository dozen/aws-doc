[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift delete-cluster-parameter-group:


******************************
delete-cluster-parameter-group
******************************



===========
Description
===========



Deletes a specified Amazon Redshift parameter group. 

.. note::

  You cannot delete a parameter group if it is associated with a cluster.

 



========
Synopsis
========

::

    delete-cluster-parameter-group
  --parameter-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--parameter-group-name`` (string)


  The name of the parameter group to be deleted. 

   

  Constraints:

   

   
  * Must be the name of an existing cluster parameter group.
   
  * Cannot delete a default cluster parameter group.
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Delete a Cluster Parameter Group
--------------------------------

This example deletes a cluster parameter group.

Command::

   aws redshift delete-cluster-parameter-group --parameter-group-name myclusterparametergroup



======
Output
======

None