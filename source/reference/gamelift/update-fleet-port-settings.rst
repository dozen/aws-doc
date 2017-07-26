[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift update-fleet-port-settings:


**************************
update-fleet-port-settings
**************************



===========
Description
===========



Updates port settings for a fleet. To update settings, specify the fleet ID to be updated and list the permissions you want to update. List the permissions you want to add in *InboundPermissionAuthorizations* , and permissions you want to remove in *InboundPermissionRevocations* . Permissions to be removed must match existing fleet permissions. If successful, the fleet ID for the updated fleet is returned.



========
Synopsis
========

::

    update-fleet-port-settings
  --fleet-id <value>
  [--inbound-permission-authorizations <value>]
  [--inbound-permission-revocations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for the fleet you want to update port settings for. 

  

``--inbound-permission-authorizations`` (list)


  Collection of port settings to be added to the fleet record.

  



Shorthand Syntax::

    FromPort=integer,ToPort=integer,IpRange=string,Protocol=string ...




JSON Syntax::

  [
    {
      "FromPort": integer,
      "ToPort": integer,
      "IpRange": "string",
      "Protocol": "TCP"|"UDP"
    }
    ...
  ]



``--inbound-permission-revocations`` (list)


  Collection of port settings to be removed from the fleet record.

  



Shorthand Syntax::

    FromPort=integer,ToPort=integer,IpRange=string,Protocol=string ...




JSON Syntax::

  [
    {
      "FromPort": integer,
      "ToPort": integer,
      "IpRange": "string",
      "Protocol": "TCP"|"UDP"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FleetId -> (string)

  

  Unique identifier for the updated fleet.

  

  

