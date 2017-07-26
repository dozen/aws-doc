[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift update-alias:


************
update-alias
************



===========
Description
===========



Updates properties for an alias. To update properties, specify the alias ID to be updated and provide the information to be changed. To reassign an alias to another fleet, provide an updated routing strategy. If successful, the updated alias record is returned.

 

Alias-related operations include:

 

 
*  create-alias   
 
*  list-aliases   
 
*  describe-alias   
 
*  update-alias   
 
*  delete-alias   
 
*  resolve-alias   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/UpdateAlias>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--alias-id`` (string)


  Unique identifier for a fleet alias. Specify the alias you want to update.

  

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

  

  Object that contains the updated alias configuration.

  

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

    

    

  

