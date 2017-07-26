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

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/DeleteClusterParameterGroup>`_


========
Synopsis
========

::

    delete-cluster-parameter-group
  --parameter-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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