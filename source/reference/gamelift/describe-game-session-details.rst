[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-game-session-details:


*****************************
describe-game-session-details
*****************************



===========
Description
===========



Retrieves properties, including the protection policy in force, for one or more game sessions. This action can be used in several ways: (1) provide a ``GameSessionId`` or ``GameSessionArn`` to request details for a specific game session; (2) provide either a ``fleet-id`` or an ``alias-id`` to request properties for all game sessions running on a fleet. 

 

To get game session record(s), specify just one of the following: game session ID, fleet ID, or alias ID. You can filter this request by game session status. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  GameSessionDetail object is returned for each session matching the request.

 

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
   

 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeGameSessionDetails>`_


========
Synopsis
========

::

    describe-game-session-details
  [--fleet-id <value>]
  [--game-session-id <value>]
  [--alias-id <value>]
  [--status-filter <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet to retrieve all game sessions active on the fleet.

  

``--game-session-id`` (string)


  Unique identifier for the game session to retrieve.

  

``--alias-id`` (string)


  Unique identifier for an alias associated with the fleet to retrieve all game sessions for.

  

``--status-filter`` (string)


  Game session status to filter results on. Possible game session statuses include ``ACTIVE`` , ``TERMINATED`` , ``ACTIVATING`` and ``TERMINATING`` (the last two are transitory). 

  

``--limit`` (integer)


  Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

  

``--next-token`` (string)


  Token that indicates the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GameSessionDetails -> (list)

  

  Collection of objects containing game session properties and the protection policy currently in force for each session matching the request.

  

  (structure)

    

    A game session's properties plus the protection policy currently in force.

    

    GameSession -> (structure)

      

      Object that describes a game session.

      

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

        

        

      

    ProtectionPolicy -> (string)

      

      Current status of protection for the game session.

       

       
      * **NoProtection** – The game session can be terminated during a scale-down event. 
       
      * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event. 
       

      

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

