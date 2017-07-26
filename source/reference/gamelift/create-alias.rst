[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift create-alias:


************
create-alias
************



===========
Description
===========



Creates an alias for a fleet. In most situations, you can use an alias ID in place of a fleet ID. By using a fleet alias instead of a specific fleet ID, you can switch gameplay and players to a new fleet without changing your game client or other game components. For example, for games in production, using an alias allows you to seamlessly redirect your player base to a new game server update. 

 

Amazon GameLift supports two types of routing strategies for aliases: simple and terminal. A simple alias points to an active fleet. A terminal alias is used to display messaging or link to a URL instead of routing players to an active fleet. For example, you might use a terminal alias when a game version is no longer supported and you want to direct players to an upgrade site. 

 

To create a fleet alias, specify an alias name, routing strategy, and optional description. Each simple alias can point to only one fleet, but a fleet can have multiple aliases. If successful, a new alias record is returned, including an alias ID, which you can reference when creating a game session. You can reassign an alias to another fleet by calling ``update-alias`` .

 

Alias-related operations include:

 

 
*  create-alias   
 
*  list-aliases   
 
*  describe-alias   
 
*  update-alias   
 
*  delete-alias   
 
*  resolve-alias   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/CreateAlias>`_


========
Synopsis
========

::

    create-alias
  --name <value>
  [--description <value>]
  --routing-strategy <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Descriptive label that is associated with an alias. Alias names do not need to be unique.

  

``--description`` (string)


  Human-readable description of an alias.

  

``--routing-strategy`` (structure)


  Object that specifies the fleet and routing type to use for the alias.

  



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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Alias -> (structure)

  

  Object that describes the newly created alias record.

  

  AliasId -> (string)

    

    Unique identifier for an alias; alias IDs are unique within a region.

    

    

  Name -> (string)

    

    Descriptive label that is associated with an alias. Alias names do not need to be unique.

    

    

  AliasArn -> (string)

    

    Unique identifier for an alias; alias ARNs are unique across all regions.

    

    

  Description -> (string)

    

    Human-readable description of an alias.

    

    

  RoutingStrategy -> (structure)

    

    Alias configuration for the alias, including routing type and settings.

    

    Type -> (string)

      

      Type of routing strategy.

       

      Possible routing types include the following:

       

       
      * **SIMPLE** – The alias resolves to one specific fleet. Use this type when routing to active fleets. 
       
      * **TERMINAL** – The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  routing-strategy message embedded. 
       

      

      

    FleetId -> (string)

      

      Unique identifier for a fleet that the alias points to.

      

      

    Message -> (string)

      

      Message text to be used with a terminal routing strategy.

      

      

    

  CreationTime -> (timestamp)

    

    Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

    

    

  LastUpdatedTime -> (timestamp)

    

    Time stamp indicating when this data object was last modified. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

    

    

  

