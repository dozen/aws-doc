[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift search-game-sessions:


********************
search-game-sessions
********************



===========
Description
===========



Retrieves a set of game sessions that match a set of search criteria and sorts them in a specified order. A game session search is limited to a single fleet. Search results include only game sessions that are in ``ACTIVE`` status. If you need to retrieve game sessions with a status other than active, use  describe-game-sessions . If you need to retrieve the protection policy for each game session, use  describe-game-session-details .

 

You can search or sort by the following game session attributes:

 

 
* **gameSessionId** -- Unique identifier for the game session. You can use either a ``GameSessionId`` or ``GameSessionArn`` value.  
 
* **gameSessionName** -- Name assigned to a game session. This value is set when requesting a new game session with  create-game-session or updating with  update-game-session . Game session names do not need to be unique to a game session. 
 
* **creationTimeMillis** -- Value indicating when a game session was created. It is expressed in Unix time as milliseconds. 
 
* **playerSessionCount** -- Number of players currently connected to a game session. This value changes rapidly as players join the session or drop out. 
 
* **maximumSessions** -- Maximum number of player sessions allowed for a game session. This value is set when requesting a new game session with  create-game-session or updating with  update-game-session . 
 
* **hasAvailablePlayerSessions** -- Boolean value indicating whether a game session has reached its maximum number of players. When searching with this attribute, the search value must be ``true`` or ``false`` . It is highly recommended that all search requests include this filter attribute to optimize search performance and return only sessions that players can join.  
 

 

To search or sort, specify either a fleet ID or an alias ID, and provide a search filter expression, a sort expression, or both. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a collection of  GameSession objects matching the request is returned.

 

.. note::

   

  Returned values for ``playerSessionCount`` and ``hasAvailablePlayerSessions`` change quickly as players join sessions and others drop out. Results should be considered a snapshot in time. Be sure to refresh search results often, and handle sessions that fill up before a player can join. 

   

 

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
   

 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/SearchGameSessions>`_


========
Synopsis
========

::

    search-game-sessions
  [--fleet-id <value>]
  [--alias-id <value>]
  [--filter-expression <value>]
  [--sort-expression <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet to search for active game sessions. Each request must reference either a fleet ID or alias ID, but not both.

  

``--alias-id`` (string)


  Unique identifier for an alias associated with the fleet to search for active game sessions. Each request must reference either a fleet ID or alias ID, but not both.

  

``--filter-expression`` (string)


  String containing the search criteria for the session search. If no filter expression is included, the request returns results for all game sessions in the fleet that are in ``ACTIVE`` status.

   

  A filter expression can contain one or multiple conditions. Each condition consists of the following:

   

   
  * **Operand** -- Name of a game session attribute. Valid values are ``gameSessionName`` , ``gameSessionId`` , ``creationTimeMillis`` , ``playerSessionCount`` , ``maximumSessions`` , ``hasAvailablePlayerSessions`` . 
   
  * **Comparator** -- Valid comparators are: ``=`` , ```` , ```` , ```` , ``=`` , ``=`` .  
   
  * **Value** -- Value to be searched for. Values can be numbers, boolean values (true/false) or strings. String values are case sensitive, enclosed in single quotes. Special characters must be escaped. Boolean and string values can only be used with the comparators ``=`` and ```` . For example, the following filter expression searches on ``gameSessionName`` : "``FilterExpression": "gameSessionName = 'Matt\\'s Awesome Game 1'"`` .  
   

   

  To chain multiple conditions in a single expression, use the logical keywords ``AND`` , ``OR`` , and ``NOT`` and parentheses as needed. For example: ``x AND y AND NOT z`` , ``NOT (x OR y)`` .

   

  Session search evaluates conditions from left to right using the following precedence rules:

   

   
  * ``=`` , ```` , ```` , ```` , ``=`` , ``=``   
   
  * Parentheses 
   
  * NOT 
   
  * AND 
   
  * OR 
   

   

  For example, this filter expression retrieves game sessions hosting at least ten players that have an open player slot: ``"maximumSessions=10 AND hasAvailablePlayerSessions=true"`` . 

  

``--sort-expression`` (string)


  Instructions on how to sort the search results. If no sort expression is included, the request returns results in random order. A sort expression consists of the following elements:

   

   
  * **Operand** -- Name of a game session attribute. Valid values are ``gameSessionName`` , ``gameSessionId`` , ``creationTimeMillis`` , ``playerSessionCount`` , ``maximumSessions`` , ``hasAvailablePlayerSessions`` . 
   
  * **Order** -- Valid sort orders are ``ASC`` (ascending) and ``DESC`` (descending). 
   

   

  For example, this sort expression returns the oldest active sessions first: ``"SortExpression": "creationTimeMillis ASC"`` . Results with a null value for the sort operand are returned at the end of the list.

  

``--limit`` (integer)


  Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages. The maximum number of results returned is 20, even if this value is not set or is set higher than 20. 

  

``--next-token`` (string)


  Token that indicates the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GameSessions -> (list)

  

  Collection of objects containing game session properties for each session matching the request.

  

  (structure)

    

    Properties describing a game session.

     

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

      

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

