[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-game-session-placement:


*******************************
describe-game-session-placement
*******************************



===========
Description
===========



Retrieves properties and current status of a game session placement request. To get game session placement details, specify the placement ID. If successful, a  GameSessionPlacement object is returned.

 

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
   

 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeGameSessionPlacement>`_


========
Synopsis
========

::

    describe-game-session-placement
  --placement-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--placement-id`` (string)


  Unique identifier for a game session placement to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GameSessionPlacement -> (structure)

  

  Object that describes the requested game session placement.

  

  PlacementId -> (string)

    

    Unique identifier for a game session placement.

    

    

  GameSessionQueueName -> (string)

    

    Descriptive label that is associated with queue. Queue names must be unique within each region.

    

    

  Status -> (string)

    

    Current status of the game session placement request.

     

     
    * **PENDING** – The placement request is currently in the queue waiting to be processed. 
     
    * **FULFILLED** – A new game session and player sessions (if requested) have been successfully created. Values for *GameSessionArn* and *GameSessionRegion* are available.  
     
    * **CANCELLED** – The placement request was canceled with a call to  stop-game-session-placement . 
     
    * **TIMED_OUT** – A new game session was not successfully created before the time limit expired. You can resubmit the placement request as needed. 
     

    

    

  GameProperties -> (list)

    

    Set of developer-defined properties for a game session. These properties are passed to the server process hosting the game session.

    

    (structure)

      

      Set of key-value pairs containing information a server process requires to set up a game session. This object allows you to pass in any set of data needed for your game. For more information, see the `Amazon GameLift Developer Guide <http://docs.aws.amazon.com/gamelift/latest/developerguide/>`_ .

      

      Key -> (string)

        

        TBD

        

        

      Value -> (string)

        

        TBD

        

        

      

    

  MaximumPlayerSessionCount -> (integer)

    

    Maximum number of players that can be connected simultaneously to the game session.

    

    

  GameSessionName -> (string)

    

    Descriptive label that is associated with a game session. Session names do not need to be unique.

    

    

  GameSessionId -> (string)

    

    Unique identifier for the game session. This value is set once the new game session is placed (placement status is Fulfilled).

    

    

  GameSessionArn -> (string)

    

    Identifier for the game session created by this placement request. This value is set once the new game session is placed (placement status is Fulfilled). This identifier is unique across all regions. You can use this value as a ``GameSessionId`` value as needed.

    

    

  GameSessionRegion -> (string)

    

    Name of the region where the game session created by this placement request is running. This value is set once the new game session is placed (placement status is Fulfilled).

    

    

  PlayerLatencies -> (list)

    

    Set of values, expressed in milliseconds, indicating the amount of latency that players are experiencing when connected to AWS regions.

    

    (structure)

      

      Regional latency information for a player, used when requesting a new game session with  start-game-session-placement . This value indicates the amount of time lag that exists when the player is connected to a fleet in the specified region. The relative difference between a player's latency values for multiple regions are used to determine which fleets are best suited to place a new game session for the player. 

      

      PlayerId -> (string)

        

        Unique identifier for a player associated with the latency data.

        

        

      RegionIdentifier -> (string)

        

        Name of the region that is associated with the latency value.

        

        

      LatencyInMilliseconds -> (float)

        

        Amount of time that represents the time lag experienced by the player when connected to the specified region.

        

        

      

    

  StartTime -> (timestamp)

    

    Time stamp indicating when this request was placed in the queue. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

    

    

  EndTime -> (timestamp)

    

    Time stamp indicating when this request was completed, canceled, or timed out.

    

    

  IpAddress -> (string)

    

    IP address of the game session. To connect to a Amazon GameLift game server, an app needs both the IP address and port number. This value is set once the new game session is placed (placement status is Fulfilled). 

    

    

  Port -> (integer)

    

    Port number for the game session. To connect to a Amazon GameLift game server, an app needs both the IP address and port number. This value is set once the new game session is placed (placement status is Fulfilled).

    

    

  PlacedPlayerSessions -> (list)

    

    Collection of information on player sessions created in response to the game session placement request. These player sessions are created only once a new game session is successfully placed (placement status is Fulfilled). This information includes the player ID (as provided in the placement request) and the corresponding player session ID. Retrieve full player sessions by calling  describe-player-sessions with the player session ID.

    

    (structure)

      

      Information about a player session that was created as part of a  start-game-session-placement request. This object contains only the player ID and player session ID. To retrieve full details on a player session, call  describe-player-sessions with the player session ID.

       

      Player-session-related operations include:

       

       
      *  create-player-session   
       
      *  create-player-sessions   
       
      *  describe-player-sessions   
       
      * Game session placements 

         
        *  start-game-session-placement   
         
        *  describe-game-session-placement   
         
        *  stop-game-session-placement   
         

       
       

      

      PlayerId -> (string)

        

        Unique identifier for a player that is associated with this player session.

        

        

      PlayerSessionId -> (string)

        

        Unique identifier for a player session.

        

        

      

    

  

