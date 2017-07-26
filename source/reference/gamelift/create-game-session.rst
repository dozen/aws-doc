[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift create-game-session:


*******************
create-game-session
*******************



===========
Description
===========



Creates a multiplayer game session for players. This action creates a game session record and assigns the new session to an instance in the specified fleet, which activates the server initialization process in your game server. A fleet must be in an ACTIVE state before a game session can be created for it.

 

To create a game session, specify either a fleet ID or an alias ID and indicate the maximum number of players the game session allows. You can also provide a name and a set of properties for your game (optional). If successful, a  GameSession object is returned containing session properties, including an IP address. By default, newly created game sessions are set to accept adding any new players to the game session. Use  update-game-session to change the creation policy.



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
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet. Each request must reference either a fleet ID or alias ID, but not both.

  

``--alias-id`` (string)


  Unique identifier for a fleet alias. Each request must reference either a fleet ID or alias ID, but not both.

  

``--maximum-player-session-count`` (integer)


  Maximum number of players that can be connected simultaneously to the game session. 

  

``--name`` (string)


  Descriptive label associated with this game session. Session names do not need to be unique.

  

``--game-properties`` (list)


  Set of properties used to administer a game session. These properties are passed to your game server.

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GameSession -> (structure)

  

  Object containing the newly created game session record.

  

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

    

    

  



.. _Amazon GameLift Developer Guide: http://docs.aws.amazon.com/gamelift/latest/developerguide/
