[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds delete-db-parameter-group:


*************************
delete-db-parameter-group
*************************



===========
Description
===========



Deletes a specified DBParameterGroup. The DBParameterGroup to be deleted cannot be associated with any DB instances.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DeleteDBParameterGroup>`_


========
Synopsis
========

::

    delete-db-parameter-group
  --db-parameter-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None