[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-fleet-port-settings:


****************************
describe-fleet-port-settings
****************************



===========
Description
===========



Retrieves the port settings for a fleet. Port settings are used to limit incoming traffic access to game servers in the fleet. To get a fleet's port settings, specify a fleet ID. If successful, an  IpPermission object is returned for the requested fleet ID. If the requested fleet has been deleted, the result set will be empty.



========
Synopsis
========

::

    describe-fleet-port-settings
  --fleet-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for the fleet you want to retrieve port settings for. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

InboundPermissions -> (list)

  

  Object containing port settings for the requested fleet ID.

  

  (structure)

    

    IP addresses and port settings used to limit access by incoming traffic (players) to a fleet. Permissions specify a range of IP addresses and port settings that must be used to gain access to a game server on a fleet machine.

    

    FromPort -> (integer)

      

      Starting value for a range of allowed port numbers. 

      

      

    ToPort -> (integer)

      

      Ending value for a range of allowed port numbers. Port numbers are end-inclusive. This value must be higher than *FromPort* .

      

      

    IpRange -> (string)

      

      Range of allowed IP addresses. This value must be expressed in `CIDR notation`_ . Example: "``000.000.000.000/[subnet mask]`` " or optionally the shortened version "``0.0.0.0/[subnet mask]`` ".

      

      

    Protocol -> (string)

      

      Network communication protocol used by the fleet.

      

      

    

  



.. _CIDR notation: https://tools.ietf.org/id/cidr
