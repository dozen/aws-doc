[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift create-game-session-queue:


*************************
create-game-session-queue
*************************



===========
Description
===========



Establishes a new queue for processing requests to place new game sessions. A queue identifies where new game sessions can be hosted -- by specifying a list of destinations (fleets or aliases) -- and how long requests can wait in the queue before timing out. You can set up a queue to try to place game sessions on fleets in multiple regions. To add placement requests to a queue, call  start-game-session-placement and reference the queue name.

 

 **Destination order.** When processing a request for a game session, Amazon GameLift tries each destination in order until it finds one with available resources to host the new game session. A queue's default order is determined by how destinations are listed. The default order is overridden when a game session placement request provides player latency information. Player latency information enables Amazon GameLift to prioritize destinations where players report the lowest average latency, as a result placing the new game session where the majority of players will have the best possible gameplay experience.

 

 **Player latency policies.** For placement requests containing player latency information, use player latency policies to protect individual players from very high latencies. With a latency cap, even when a destination can deliver a low latency for most players, the game is not placed where any individual player is reporting latency higher than a policy's maximum. A queue can have multiple latency policies, which are enforced consecutively starting with the policy with the lowest latency cap. Use multiple policies to gradually relax latency controls; for example, you might set a policy with a low latency cap for the first 60 seconds, a second policy with a higher cap for the next 60 seconds, etc. 

 

To create a new queue, provide a name, timeout value, a list of destinations and, if desired, a set of latency policies. If successful, a new queue object is returned.

 

Queue-related operations include:

 

 
*  create-game-session-queue   
 
*  describe-game-session-queues   
 
*  update-game-session-queue   
 
*  delete-game-session-queue   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/CreateGameSessionQueue>`_


========
Synopsis
========

::

    create-game-session-queue
  --name <value>
  [--timeout-in-seconds <value>]
  [--player-latency-policies <value>]
  [--destinations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Descriptive label that is associated with queue. Queue names must be unique within each region.

  

``--timeout-in-seconds`` (integer)


  Maximum time, in seconds, that a new game session placement request remains in the queue. When a request exceeds this time, the game session placement changes to a TIMED_OUT status.

  

``--player-latency-policies`` (list)


  Collection of latency policies to apply when processing game sessions placement requests with player latency information. Multiple policies are evaluated in order of the maximum latency value, starting with the lowest latency values. With just one policy, it is enforced at the start of the game session placement for the duration period. With multiple policies, each policy is enforced consecutively for its duration period. For example, a queue might enforce a 60-second policy followed by a 120-second policy, and then no policy for the remainder of the placement. A player latency policy must set a value for MaximumIndividualPlayerLatencyMilliseconds; if none is set, this API requests will fail.

  



Shorthand Syntax::

    MaximumIndividualPlayerLatencyMilliseconds=integer,PolicyDurationSeconds=integer ...




JSON Syntax::

  [
    {
      "MaximumIndividualPlayerLatencyMilliseconds": integer,
      "PolicyDurationSeconds": integer
    }
    ...
  ]



``--destinations`` (list)


  List of fleets that can be used to fulfill game session placement requests in the queue. Fleets are identified by either a fleet ARN or a fleet alias ARN. Destinations are listed in default preference order.

  



Shorthand Syntax::

    DestinationArn=string ...




JSON Syntax::

  [
    {
      "DestinationArn": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GameSessionQueue -> (structure)

  

  Object that describes the newly created game session queue.

  

  Name -> (string)

    

    Descriptive label that is associated with queue. Queue names must be unique within each region.

    

    

  GameSessionQueueArn -> (string)

    

    Amazon Resource Name (`ARN <http://docs.aws.amazon.com/AmazonS3/latest/dev/s3-arn-format.html>`_ ) that is assigned to a game session queue and uniquely identifies it. Format is ``arn:aws:gamelift:region::fleet/fleet-a1234567-b8c9-0d1e-2fa3-b45c6d7e8912`` .

    

    

  TimeoutInSeconds -> (integer)

    

    Maximum time, in seconds, that a new game session placement request remains in the queue. When a request exceeds this time, the game session placement changes to a TIMED_OUT status.

    

    

  PlayerLatencyPolicies -> (list)

    

    Collection of latency policies to apply when processing game sessions placement requests with player latency information. Multiple policies are evaluated in order of the maximum latency value, starting with the lowest latency values. With just one policy, it is enforced at the start of the game session placement for the duration period. With multiple policies, each policy is enforced consecutively for its duration period. For example, a queue might enforce a 60-second policy followed by a 120-second policy, and then no policy for the remainder of the placement. 

    

    (structure)

      

      Queue setting that determines the highest latency allowed for individual players when placing a game session. When a latency policy is in force, a game session cannot be placed at any destination in a region where a player is reporting latency higher than the cap. Latency policies are only enforced when the placement request contains player latency information.

       

      Queue-related operations include:

       

       
      *  create-game-session-queue   
       
      *  describe-game-session-queues   
       
      *  update-game-session-queue   
       
      *  delete-game-session-queue   
       

      

      MaximumIndividualPlayerLatencyMilliseconds -> (integer)

        

        The maximum latency value that is allowed for any player, in milliseconds. All policies must have a value set for this property.

        

        

      PolicyDurationSeconds -> (integer)

        

        The length of time, in seconds, that the policy is enforced while placing a new game session. A null value for this property means that the policy is enforced until the queue times out.

        

        

      

    

  Destinations -> (list)

    

    List of fleets that can be used to fulfill game session placement requests in the queue. Fleets are identified by either a fleet ARN or a fleet alias ARN. Destinations are listed in default preference order.

    

    (structure)

      

      Fleet designated in a game session queue. Requests for new game sessions in the queue are fulfilled by starting a new game session on any destination configured for a queue. 

       

      Queue-related operations include:

       

       
      *  create-game-session-queue   
       
      *  describe-game-session-queues   
       
      *  update-game-session-queue   
       
      *  delete-game-session-queue   
       

      

      DestinationArn -> (string)

        

        Amazon Resource Name (ARN) assigned to fleet or fleet alias. ARNs, which include a fleet ID or alias ID and a region name, provide a unique identifier across all regions. 

        

        

      

    

  

