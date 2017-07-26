[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift update-game-session:


*******************
update-game-session
*******************



===========
Description
===========



Updates game session properties. This includes the session name, maximum player count and the player session creation policy, which either allows or denies new players from joining the session. To update a game session, specify the game session ID and the values you want to change. If successful, an updated  GameSession object is returned. 



========
Synopsis
========

::

    update-game-session
  --game-session-id <value>
  [--maximum-player-session-count <value>]
  [--name <value>]
  [--player-session-creation-policy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--game-session-id`` (string)


  Unique identifier for a game session. Specify the game session you want to update. 

  

``--maximum-player-session-count`` (integer)


  Maximum number of players that can be simultaneously connected to the game session.

  

``--name`` (string)


  Descriptive label associated with this game session. Session names do not need to be unique.

  

``--player-session-creation-policy`` (string)


  Policy determining whether or not the game session accepts new players.

  

  Possible values:

  
  *   ``ACCEPT_ALL``

  
  *   ``DENY_ALL``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GameSession -> (structure)

  

  Object containing the updated game session metadata.

  

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
