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

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DeleteDBSubnetGroup>`_


========
Synopsis
========

::

    delete-db-subnet-group
  --db-subnet-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-subnet-group-name`` (string)


  The name of the database subnet group to delete.

   

  .. note::

     

    You cannot delete the default subnet group.

     

   

  Constraints:

   

  Constraints: Must contain no more than 255 alphanumeric characters, periods, underscores, spaces, or hyphens. Must not be default.

   

  Example: ``mySubnetgroup``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None