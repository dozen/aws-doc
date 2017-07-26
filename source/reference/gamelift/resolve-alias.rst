[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift resolve-alias:


*************
resolve-alias
*************



===========
Description
===========



Retrieves the fleet ID that a specified alias is currently pointing to. 



========
Synopsis
========

::

    resolve-alias
  --alias-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--alias-id`` (string)


  Unique identifier for the alias you want to resolve. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FleetId -> (string)

  

  Fleet ID associated with the requested alias.

  

  

