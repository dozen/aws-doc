[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-player-sessions:


************************
describe-player-sessions
************************



===========
Description
===========



Retrieves properties for one or more player sessions. This action can be used in several ways: (1) provide a *player-session-id* parameter to request properties for a specific player session; (2) provide a *game-session-id* parameter to request properties for all player sessions in the specified game session; (3) provide a *PlayerId* parameter to request properties for all player sessions of a specified player. 

 

To get game session record(s), specify only one of the following: a player session ID, a game session ID, or a player ID. You can filter this request by player session status. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  PlayerSession object is returned for each session matching the request.



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
  [--generate-cli-skeleton]




=======
Options
=======

``--game-session-id`` (string)


  Unique identifier for a game session.

  

``--player-id`` (string)


  Unique identifier for a player.

  

``--player-session-id`` (string)


  Unique identifier for a player session.

  

``--player-session-status-filter`` (string)


  Player session status to filter results on. Possible player session states include: 

  
  * RESERVED: The player session request has been received, but the player has not yet connected to the game server and/or been validated. 
  
  * ACTIVE: The player has been validated by the game server and is currently connected.
  
  * COMPLETED: The player connection has been dropped.
  
  * TIMEDOUT: A player session request was received, but the player did not connect and/or was not validated within the time-out limit (60 seconds).
  

  

  

``--limit`` (integer)


  Maximum number of results to return. You can use this parameter with *NextToken* to get results as a set of sequential pages. If a player session ID is specified, this parameter is ignored.

  

``--next-token`` (string)


  Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value. If a player session ID is specified, this parameter is ignored.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

PlayerSessions -> (list)

  

  Collection of objects containing properties for each player session that matches the request.

  

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

      

      

    

  

NextToken -> (string)

  

  Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

   

  .. note::

    

    If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

    

  

  

