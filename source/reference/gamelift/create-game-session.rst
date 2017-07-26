[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift create-game-session:


*******************
create-game-session
*******************



===========
Description
===========



Creates a multiplayer game session for players. This action creates a game session record and assigns an available server process in the specified fleet to host the game session. A fleet must have an ``ACTIVE`` status before a game session can be created in it.

 

To create a game session, specify either fleet ID or alias ID and indicate a maximum number of players to allow in the game session. You can also provide a name and game-specific properties for this game session. If successful, a  GameSession object is returned containing game session properties, including a game session ID with the custom string you provided.

 

 **Idempotency tokens.** You can add a token that uniquely identifies game session requests. This is useful for ensuring that game session requests are idempotent. Multiple requests with the same idempotency token are processed only once; subsequent requests return the original result. All response values are the same with the exception of game session status, which may change.

 

 **Resource creation limits.** If you are creating a game session on a fleet with a resource creation limit policy in force, then you must specify a creator ID. Without this ID, Amazon GameLift has no way to evaluate the policy for this new game session request.

 

By default, newly created game sessions allow new players to join. Use  update-game-session to change the game session's player session creation policy.

 

 *Available in Amazon GameLift Local.*  

 

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
   

 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/CreateGameSession>`_


========
Synopsis
========

::

    create-game-session
  [--fleet-id <value>]
  [--alias-id <value>]
  --maximum-player-session-count <value>
  [--name <value>]
  [--game-properties <value>]
  [--creator-id <value>]
  [--game-session-id <value>]
  [--idempotency-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet to create a game session in. Each request must reference either a fleet ID or alias ID, but not both.

  

``--alias-id`` (string)


  Unique identifier for an alias associated with the fleet to create a game session in. Each request must reference either a fleet ID or alias ID, but not both.

  

``--maximum-player-session-count`` (integer)


  Maximum number of players that can be connected simultaneously to the game session.

  

``--name`` (string)


  Descriptive label that is associated with a game session. Session names do not need to be unique.

  

``--game-properties`` (list)


  Set of developer-defined properties for a game session. These properties are passed to the server process hosting the game session.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--creator-id`` (string)


  Unique identifier for a player or entity creating the game session. This ID is used to enforce a resource protection policy (if one exists) that limits the number of concurrent active game sessions one player can have.

  

``--game-session-id`` (string)


   *This parameter is no longer preferred. Please use ``IdempotencyToken`` instead.* Custom string that uniquely identifies a request for a new game session. Maximum token length is 48 characters. If provided, this string is included in the new game session's ID. (A game session ID has the following format: ``arn:aws:gamelift:region::gamesession/fleet ID/custom ID string or idempotency token`` .) 

  

``--idempotency-token`` (string)


  Custom string that uniquely identifies a request for a new game session. Maximum token length is 48 characters. If provided, this string is included in the new game session's ID. (A game session ID has the following format: ``arn:aws:gamelift:region::gamesession/fleet ID/custom ID string or idempotency token`` .) 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GameSession -> (structure)

  

  Object that describes the newly created game session record.

  

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

    

    

  

