[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-game-sessions:


**********************
describe-game-sessions
**********************



===========
Description
===========



Retrieves properties for one or more game sessions. This action can be used in several ways: (1) provide a *game-session-id* parameter to request properties for a specific game session; (2) provide a *fleet-id* or *alias-id* parameter to request properties for all game sessions running on a fleet. 

 

To get game session record(s), specify only one of the following: game session ID, fleet ID, or alias ID. You can filter this request by game session status. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  GameSession object is returned for each session matching the request.



========
Synopsis
========

::

    describe-game-sessions
  [--fleet-id <value>]
  [--game-session-id <value>]
  [--alias-id <value>]
  [--status-filter <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet. Specify a fleet to retrieve information on all game sessions active on the fleet.

  

``--game-session-id`` (string)


  Unique identifier for a game session. Specify the game session to retrieve information on.

  

``--alias-id`` (string)


  Unique identifier for a fleet alias. Specify an alias to retrieve information on all game sessions active on the fleet.

  

``--status-filter`` (string)


  Game session status to filter results on. Possible game session states include ACTIVE, TERMINATED, ACTIVATING and TERMINATING (the last two are transitory). 

  

``--limit`` (integer)


  Maximum number of results to return. You can use this parameter with *NextToken* to get results as a set of sequential pages.

  

``--next-token`` (string)


  Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GameSessions -> (list)

  

  Collection of objects containing game session properties for each session matching the request.

  

  (structure)

    

    Properties describing a game session.

    

    GameSessionId -> (string)

      

      Unique identifier for a game session.

      

      

    Name -> (string)

      

      Descriptive label associated with this game session. Session names do not need to be unique.

      

      

    FleetId -> (string)

      

      Unique identifier for a fleet.

      

      

    CreationTime -> (timestamp)

      

      Time stamp indicating when this object was created. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

      

      

    TerminationTime -> (timestamp)

      

      Time stamp indicating when this fleet was terminated. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

      

      

    CurrentPlayerSessionCount -> (integer)

      

      Number of players currently in the game session.

      

      

    MaximumPlayerSessionCount -> (integer)

      

      Maximum number of players allowed in the game session.

      

      

    Status -> (string)

      

      Current status of the game session. A game session must be in an ACTIVE state to have player sessions.

      

      

    GameProperties -> (list)

      

      Set of custom properties for the game session.

      

      (structure)

        

        Set of key-value pairs containing information your game server requires to set up sessions. This object allows you to pass in any set of data needed for your game. For more information, see the `Amazon GameLift Developer Guide`_ .

        

        Key -> (string)

          

          

        Value -> (string)

          

          

        

      

    IpAddress -> (string)

      

      IP address of the game session.

      

      

    PlayerSessionCreationPolicy -> (string)

      

      Indicates whether or not the game session is accepting new players.

      

      

    

  

NextToken -> (string)

  

  Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

   

  .. note::

    

    If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

    

  

  



.. _Amazon GameLift Developer Guide: http://docs.aws.amazon.com/gamelift/latest/developerguide/
