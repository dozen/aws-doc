[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift update-game-session:


*******************
update-game-session
*******************



===========
Description
===========



Updates game session properties. This includes the session name, maximum player count, protection policy, which controls whether or not an active game session can be terminated during a scale-down event, and the player session creation policy, which controls whether or not new players can join the session. To update a game session, specify the game session ID and the values you want to change. If successful, an updated  GameSession object is returned. 

 

Game-session-related operations include:

 

 
*  create-game-session   
 
*  describe-game-sessions   
 
*  describe-game-session-details   
 
*  search-game-sessions   
 
*  update-game-session   
 
*  get-game-session-log-url   
 
* Game session placements 

   
  *  start-game-session-placement   
   
  *  describe-game-session-placement   
   
  *  stop-game-session-placement   
   

 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/UpdateGameSession>`_


========
Synopsis
========

::

    update-game-session
  --game-session-id <value>
  [--maximum-player-session-count <value>]
  [--name <value>]
  [--player-session-creation-policy <value>]
  [--protection-policy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--game-session-id`` (string)


  Unique identifier for the game session to update.

  

``--maximum-player-session-count`` (integer)


  Maximum number of players that can be connected simultaneously to the game session.

  

``--name`` (string)


  Descriptive label that is associated with a game session. Session names do not need to be unique.

  

``--player-session-creation-policy`` (string)


  Policy determining whether or not the game session accepts new players.

  

  Possible values:

  
  *   ``ACCEPT_ALL``

  
  *   ``DENY_ALL``

  

  

``--protection-policy`` (string)


  Game session protection policy to apply to this game session only.

   

   
  * **NoProtection** – The game session can be terminated during a scale-down event. 
   
  * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event. 
   

  

  Possible values:

  
  *   ``NoProtection``

  
  *   ``FullProtection``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GameSession -> (structure)

  

  Object that contains the updated game session metadata.

  

  GameSessionId -> (string)

    

    Unique identifier for the game session. A game session ID has the following format: ``arn:aws:gamelift:region::gamesession/fleet ID/custom ID string or idempotency token`` .

    

    

  Name -> (string)

    

    Descriptive label that is associated with a game session. Session names do not need to be unique.

    

    

  FleetId -> (string)

    

    Unique identifier for a fleet the game session is running on.

    

    

  CreationTime -> (timestamp)

    

    Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

    

    

  TerminationTime -> (timestamp)

    

    Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

    

    

  CurrentPlayerSessionCount -> (integer)

    

    Number of players currently in the game session.

    

    

  MaximumPlayerSessionCount -> (integer)

    

    Maximum number of players that can be connected simultaneously to the game session.

    

    

  Status -> (string)

    

    Current status of the game session. A game session must have an ``ACTIVE`` status to have player sessions.

    

    

  GameProperties -> (list)

    

    Set of developer-defined properties for a game session. These properties are passed to the server process hosting the game session.

    

    (structure)

      

      Set of key-value pairs containing information a server process requires to set up a game session. This object allows you to pass in any set of data needed for your game. For more information, see the `Amazon GameLift Developer Guide <http://docs.aws.amazon.com/gamelift/latest/developerguide/>`_ .

      

      Key -> (string)

        

        TBD

        

        

      Value -> (string)

        

        TBD

        

        

      

    

  IpAddress -> (string)

    

    IP address of the game session. To connect to a Amazon GameLift game server, an app needs both the IP address and port number.

    

    

  Port -> (integer)

    

    Port number for the game session. To connect to a Amazon GameLift game server, an app needs both the IP address and port number.

    

    

  PlayerSessionCreationPolicy -> (string)

    

    Indicates whether or not the game session is accepting new players.

    

    

  CreatorId -> (string)

    

    Unique identifier for a player. This ID is used to enforce a resource protection policy (if one exists), that limits the number of game sessions a player can create.

    

    

  

