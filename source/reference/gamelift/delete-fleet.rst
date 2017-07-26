[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift delete-fleet:


************
delete-fleet
************



===========
Description
===========



Deletes everything related to a fleet. Before deleting a fleet, you must set the fleet's desired capacity to zero. See  update-fleet-capacity .

 

This action removes the fleet's resources and the fleet record. Once a fleet is deleted, you can no longer use that fleet.



========
Synopsis
========

::

    delete-fleet
  --fleet-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for the fleet you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None