[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift update-alias:


************
update-alias
************



===========
Description
===========



Updates properties for an alias. To update properties, specify the alias ID to be updated and provide the information to be changed. To reassign an alias to another fleet, provide an updated routing strategy. If successful, the updated alias record is returned.



========
Synopsis
========

::

    update-alias
  --alias-id <value>
  [--name <value>]
  [--description <value>]
  [--routing-strategy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--alias-id`` (string)


  Unique identifier for a fleet alias. Specify the alias you want to update. 

  

``--name`` (string)


  Descriptive label associated with this alias. Alias names do not need to be unique.

  

``--description`` (string)


  Human-readable description of the alias.

  

``--routing-strategy`` (structure)


  Object specifying the fleet and routing type to use for the alias.

  



Shorthand Syntax::

    Type=string,FleetId=string,Message=string




JSON Syntax::

  {
    "Type": "SIMPLE"|"TERMINAL",
    "FleetId": "string",
    "Message": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Alias -> (structure)

  

  Object containing the updated alias configuration.

  

  AliasId -> (string)

    

    Unique identifier for a fleet alias.

    

    

  Name -> (string)

    

    Descriptive label associated with this alias. Alias names do not need to be unique.

    

    

  Description -> (string)

    

    Human-readable description of the alias.

    

    

  RoutingStrategy -> (structure)

    

    Routing configuration for a fleet alias. 

    

    Type -> (string)

      

      Type of routing strategy. Possible routing types include: 

      
      * SIMPLE: The alias resolves to one specific fleet. Use this type when routing to active fleets.
      
      * TERMINAL: The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  routing-strategy message embedded.
      

      

      

      

    FleetId -> (string)

      

      Unique identifier for a fleet.

      

      

    Message -> (string)

      

      Message text to be used with a terminal routing strategy.

      

      

    

  CreationTime -> (timestamp)

    

    Time stamp indicating when this object was created. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

    

    

  LastUpdatedTime -> (timestamp)

    

    Time stamp indicating when this object was last modified. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

    

    

  

