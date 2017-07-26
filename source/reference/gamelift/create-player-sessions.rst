[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift create-player-sessions:


**********************
create-player-sessions
**********************



===========
Description
===========



Adds a group of players to a game session. Similar to  create-player-session , this action allows you to add multiple players in a single call, which is useful for games that provide party and/or matchmaking features. A game session must be in an ACTIVE state, have a creation policy of ALLOW_ALL, and have an open player slot before players can be added to the session.

 

To create player sessions, specify a game session ID and a list of player IDs. If successful, the players are added to the game session and a set of new  PlayerSession objects is returned. 



========
Synopsis
========

::

    create-player-sessions
  --game-session-id <value>
  --player-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--game-session-id`` (string)


  Unique identifier for a game session. 

  

``--player-ids`` (list)


  List of unique identifiers for the players to be added.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

PlayerSessions -> (list)

  

  Collection of player session objects created for the added players.

  

  (structure)

    

    Properties describing a player session.

    

    PlayerSessionId -> (string)

      

      Unique identifier for a player session.

      

      

    PlayerId -> (string)

      

      Unique identifier for a player.

      

      

    GameSessionId -> (string)

      

      Unique identifier for a game session.

      

      

    FleetId -> (string)

      

      Unique identifier for a fleet.

      

      

    CreationTime -> (timestamp)

      

      Time stamp indicating when this object was created. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

      

      

    TerminationTime -> (timestamp)

      

      Time stamp indicating when this fleet was terminated. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

      

      

    Status -> (string)

      

      Current status of the player session. Possible player session states include: 

      
      * RESERVED: The player session request has been received, but the player has not yet connected to the game server and/or been validated. 
      
      * ACTIVE: The player has been validated by the game server and is currently connected.
      
      * COMPLETED: The player connection has been dropped.
      
      * TIMEDOUT: A player session request was received, but the player did not connect and/or was not validated within the time-out limit (60 seconds).
      

      

      

      

    IpAddress -> (string)

      

      Game session IP address. All player sessions reference the game session location. 

      

      

    

  

