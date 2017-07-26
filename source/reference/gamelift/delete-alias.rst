[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift delete-alias:


************
delete-alias
************



===========
Description
===========



Deletes an alias. This action removes all record of the alias; game clients attempting to access a game server using the deleted alias receive an error. To delete an alias, specify the alias ID to be deleted.



========
Synopsis
========

::

    delete-alias
  --alias-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--alias-id`` (string)


  Unique identifier for a fleet alias. Specify the alias you want to delete. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None