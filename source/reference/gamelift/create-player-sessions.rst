[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift create-player-sessions:


**********************
create-player-sessions
**********************



===========
Description
===========



Adds a group of players to a game session. This action is useful with a team matching feature. Before players can be added, a game session must have an ``ACTIVE`` status, have a creation policy of ``ALLOW_ALL`` , and have an open player slot. To add a single player to a game session, use  create-player-session .

 

To create player sessions, specify a game session ID, a list of player IDs, and optionally a set of player data strings. If successful, the players are added to the game session and a set of new  PlayerSession objects is returned. Player sessions cannot be updated.

 

 *Available in Amazon GameLift Local.*  

 

Player-session-related operations include:

 

 
*  create-player-session   
 
*  create-player-sessions   
 
*  describe-player-sessions   
 
* Game session placements 

   
  *  start-game-session-placement   
   
  *  describe-game-session-placement   
   
  *  stop-game-session-placement   
   

 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/CreatePlayerSessions>`_


========
Synopsis
========

::

    create-player-sessions
  --game-session-id <value>
  --player-ids <value>
  [--player-data-map <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--game-session-id`` (string)


  Unique identifier for the game session to add players to.

  

``--player-ids`` (list)


  List of unique identifiers for the players to be added.

  



Syntax::

  "string" "string" ...



``--player-data-map`` (map)


  Map of string pairs, each specifying a player ID and a set of developer-defined information related to the player. Amazon GameLift does not use this data, so it can be formatted as needed for use in the game. Player data strings for player IDs not included in the ``PlayerIds`` parameter are ignored. 

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PlayerSessions -> (list)

  

  Collection of player session objects created for the added players.

  

  (structure)

    

    Properties describing a player session. A player session represents either a player reservation for a game session or actual player activity in a game session. A player session object (including player data) is automatically passed to a game session when the player connects to the game session and is validated.

     

    Player-session-related operations include:

     

     
    *  create-player-session   
     
    *  create-player-sessions   
     
    *  describe-player-sessions   
     
    * Game session placements 

       
      *  start-game-session-placement   
       
      *  describe-game-session-placement   
       
      *  stop-game-session-placement   
       

     
     

    

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

      

      

    

  

