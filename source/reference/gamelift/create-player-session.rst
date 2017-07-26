[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift create-player-session:


*********************
create-player-session
*********************



===========
Description
===========



Adds a player to a game session and creates a player session record. Before a player can be added, a game session must have an ``ACTIVE`` status, have a creation policy of ``ALLOW_ALL`` , and have an open player slot. To add a group of players to a game session, use  create-player-sessions .

 

To create a player session, specify a game session ID, player ID, and optionally a string of player data. If successful, the player is added to the game session and a new  PlayerSession object is returned. Player sessions cannot be updated. 

 

 *Available in Amazon GameLift Local.*  

 

Player-session-related operations include:

 

 
*  create-player-session   
 
*  create-player-sessions   
 
*  describe-player-sessions   
 
* Game session placements 

   
  *  start-game-session-placement   
   
  *  describe-game-session-placement   
   
  *  stop-game-session-placement   
   

 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/CreatePlayerSession>`_


========
Synopsis
========

::

    create-player-session
  --game-session-id <value>
  --player-id <value>
  [--player-data <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--game-session-id`` (string)


  Unique identifier for the game session to add a player to.

  

``--player-id`` (string)


  Unique identifier for a player. Player IDs are developer-defined.

  

``--player-data`` (string)


  Developer-defined information related to a player. Amazon GameLift does not use this data, so it can be formatted as needed for use in the game.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PlayerSession -> (structure)

  

  Object that describes the newly created player session record.

  

  PlayerSessionId -> (string)

    

    Unique identifier for a player session.

    

    

  PlayerId -> (string)

    

    Unique identifier for a player that is associated with this player session.

    

    

  GameSessionId -> (string)

    

    Unique identifier for the game session that the player session is connected to.

    

    

  FleetId -> (string)

    

    Unique identifier for a fleet that the player's game session is running on.

    

    

  CreationTime -> (timestamp)

    

    Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

    

    

  TerminationTime -> (timestamp)

    

    Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

    

    

  Status -> (string)

    

    Current status of the player session.

     

    Possible player session statuses include the following:

     

     
    * **RESERVED** – The player session request has been received, but the player has not yet connected to the server process and/or been validated.  
     
    * **ACTIVE** – The player has been validated by the server process and is currently connected. 
     
    * **COMPLETED** – The player connection has been dropped. 
     
    * **TIMEDOUT** – A player session request was received, but the player did not connect and/or was not validated within the time-out limit (60 seconds). 
     

    

    

  IpAddress -> (string)

    

    IP address of the game session. To connect to a Amazon GameLift game server, an app needs both the IP address and port number.

    

    

  Port -> (integer)

    

    Port number for the game session. To connect to a Amazon GameLift server process, an app needs both the IP address and port number.

    

    

  PlayerData -> (string)

    

    Developer-defined information related to a player. Amazon GameLift does not use this data, so it can be formatted as needed for use in the game. 

    

    

  

