[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-player-sessions:


************************
describe-player-sessions
************************



===========
Description
===========



Retrieves properties for one or more player sessions. This action can be used in several ways: (1) provide a ``player-session-id`` to request properties for a specific player session; (2) provide a ``GameSessionId`` to request properties for all player sessions in the specified game session; (3) provide a ``PlayerId`` to request properties for all player sessions of a specified player. 

 

To get game session record(s), specify only one of the following: a player session ID, a game session ID, or a player ID. You can filter this request by player session status. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  PlayerSession object is returned for each session matching the request.

 

 *Available in Amazon GameLift Local.*  

 

Player-session-related operations include:

 

 
*  create-player-session   
 
*  create-player-sessions   
 
*  describe-player-sessions   
 
* Game session placements 

   
  *  start-game-session-placement   
   
  *  describe-game-session-placement   
   
  *  stop-game-session-placement   
   

 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribePlayerSessions>`_


========
Synopsis
========

::

    describe-player-sessions
  [--game-session-id <value>]
  [--player-id <value>]
  [--player-session-id <value>]
  [--player-session-status-filter <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--game-session-id`` (string)


  Unique identifier for the game session to retrieve player sessions for.

  

``--player-id`` (string)


  Unique identifier for a player to retrieve player sessions for.

  

``--player-session-id`` (string)


  Unique identifier for a player session to retrieve.

  

``--player-session-status-filter`` (string)


  Player session status to filter results on.

   

  Possible player session statuses include the following:

   

   
  * **RESERVED** – The player session request has been received, but the player has not yet connected to the server process and/or been validated.  
   
  * **ACTIVE** – The player has been validated by the server process and is currently connected. 
   
  * **COMPLETED** – The player connection has been dropped. 
   
  * **TIMEDOUT** – A player session request was received, but the player did not connect and/or was not validated within the time-out limit (60 seconds). 
   

  

``--limit`` (integer)


  Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages. If a player session ID is specified, this parameter is ignored.

  

``--next-token`` (string)


  Token that indicates the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value. If a player session ID is specified, this parameter is ignored.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PlayerSessions -> (list)

  

  Collection of objects containing properties for each player session that matches the request.

  

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

      

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

