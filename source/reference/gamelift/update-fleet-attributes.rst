[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift update-fleet-attributes:


***********************
update-fleet-attributes
***********************



===========
Description
===========



Updates fleet properties, including name and description, for a fleet. To update metadata, specify the fleet ID and the property values you want to change. If successful, the fleet ID for the updated fleet is returned.



========
Synopsis
========

::

    update-fleet-attributes
  --fleet-id <value>
  [--name <value>]
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for the fleet you want to update attribute metadata for. 

  

``--name`` (string)


  Descriptive label associated with this fleet. Fleet names do not need to be unique.

  

``--description`` (string)


  Human-readable description of the fleet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FleetId -> (string)

  

  Unique identifier for the updated fleet.

  

  

