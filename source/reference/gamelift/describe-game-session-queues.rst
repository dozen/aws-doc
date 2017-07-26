[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-game-session-queues:


****************************
describe-game-session-queues
****************************



===========
Description
===========



Retrieves the properties for one or more game session queues. When requesting multiple queues, use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  GameSessionQueue object is returned for each requested queue. When specifying a list of queues, objects are returned only for queues that currently exist in the region.

 

Queue-related operations include:

 

 
*  create-game-session-queue   
 
*  describe-game-session-queues   
 
*  update-game-session-queue   
 
*  delete-game-session-queue   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeGameSessionQueues>`_


========
Synopsis
========

::

    describe-game-session-queues
  [--names <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--names`` (list)


  List of queue names to retrieve information for. To request settings for all queues, leave this parameter empty.

  



Syntax::

  "string" "string" ...



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

GameSessionQueues -> (list)

  

  Collection of objects that describes the requested game session queues.

  

  (structure)

    

    Configuration of a queue that is used to process game session placement requests. The queue configuration identifies several game features:

     

    Queue-related operations include:

     

     
    *  create-game-session-queue   
     
    *  describe-game-session-queues   
     
    *  update-game-session-queue   
     
    *  delete-game-session-queue   
     

     

     
    * The destinations where a new game session can potentially be hosted. Amazon GameLift tries these destinations in an order based on either the queue's default order or player latency information, if provided in a placement request. With latency information, Amazon GameLift can place game sessions where the majority of players are reporting the lowest possible latency.  
     
    * The length of time that placement requests can wait in the queue before timing out.  
     
    * A set of optional latency policies that protect individual players from high latencies, preventing game sessions from being placed where any individual player is reporting latency higher than a policy's maximum. 
     

     

    Queue-related operations include the following:

     

     
    *  create-game-session-queue   
     
    *  describe-game-session-queues   
     
    *  update-game-session-queue   
     
    *  delete-game-session-queue   
     

    

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

          

          

        

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

