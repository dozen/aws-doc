[ :ref:`aws <cli:aws>` ]

.. _cli:aws gamelift:


********
gamelift
********



===========
Description
===========

 

Amazon GameLift is a managed service for developers who need a scalable, dedicated server solution for their multiplayer games. Amazon GameLift provides tools for the following tasks: (1) acquire computing resources and deploy game servers, (2) scale game server capacity to meet player demand, (3) host game sessions and manage player access, and (4) track in-depth metrics on player usage and server performance.

 

The Amazon GameLift service API includes two important function sets:

 

 
* **Manage game sessions and player access** – Retrieve information on available game sessions; create new game sessions; send player requests to join a game session. 
 
* **Configure and manage game server resources** – Manage builds, fleets, queues, and aliases; set autoscaling policies; retrieve logs and metrics. 
 

 

This reference guide describes the low-level service API for Amazon GameLift. You can use the API functionality with these tools: 

 

 
* The Amazon Web Services software development kit (`AWS SDK <http://aws.amazon.com/tools/#sdk>`_ ) is available in `multiple languages <http://docs.aws.amazon.com/gamelift/latest/developerguide/gamelift-supported.html#gamelift-supported-clients>`_ including C++ and C#. Use the SDK to access the API programmatically from an application, such as a game client. 
 
* The `AWS command-line interface <http://aws.amazon.com/cli/>`_ (CLI) tool is primarily useful for handling administrative actions, such as setting up and managing Amazon GameLift settings and resources. You can use the AWS CLI to manage all of your AWS services. 
 
* The `AWS Management Console <https://console.aws.amazon.com/gamelift/home>`_ for Amazon GameLift provides a web interface to manage your Amazon GameLift settings and resources. The console includes a dashboard for tracking key resources, includings builds and fleets, and displays usage and performance metrics for your games as customizable graphs. 
 
* Amazon GameLift Local is a tool for testing your game's integration with Amazon GameLift before deploying it on the service. This tools supports a subset of key API actions, which can be called from either the AWS CLI or programmatically. See `Testing an Integration <http://docs.aws.amazon.com/gamelift/latest/developerguide/integration-testing-local.html>`_ . 
 

 

 **MORE RESOURCES**  

 

 
* `Amazon GameLift Developer Guide <http://docs.aws.amazon.com/gamelift/latest/developerguide/>`_ – Learn more about Amazon GameLift features and how to use them.  
 
* `Lumberyard and Amazon GameLift Tutorials <https://gamedev.amazon.com/forums/tutorials>`_ – Get started fast with walkthroughs and sample projects. 
 
* `GameDev Blog <http://aws.amazon.com/blogs/gamedev/>`_ – Stay up to date with new features and techniques. 
 
* `GameDev Forums <https://gamedev.amazon.com/forums/spaces/123/gamelift-discussion.html>`_ – Connect with the GameDev community. 
 
* `Amazon GameLift Document History <http://docs.aws.amazon.com/gamelift/latest/developerguide/doc-history.html>`_ – See changes to the Amazon GameLift service, SDKs, and documentation, as well as links to release notes.  
 

 

 **API SUMMARY**  

 

This list offers a functional overview of the Amazon GameLift service API.

 

 **Managing Games and Players**  

 

These actions allow you to start new game sessions, find existing game sessions, track status and other game session information, and enable access for players to join game sessions.

 

 
* **Discover existing game sessions**   

   
  *  search-game-sessions – Get all available game sessions or search for game sessions that match a set of criteria.  
   

 
 
* **Start a new game session**   

   
  * Game session placement – Use a queue to process requests for new game sessions and place them on the best available fleet. Placement requests are asynchronous; game sessions are started whenever acceptable resources become available.  

     
    *  start-game-session-placement – Request a new game session placement and add one or more players to it. 
     
    *  describe-game-session-placement – Get details on a placement request, including status. 
     
    *  stop-game-session-placement – Cancel a placement request.  
     

   
   
  *  create-game-session – Request a new game session on a specific fleet. *Available in Amazon GameLift Local.*   
   

 
 
* **Manage game session data**   

   
  *  describe-game-sessions – Retrieve metadata for one or more game sessions, including length of time active and current player count. *Available in Amazon GameLift Local.*   
   
  *  describe-game-session-details – Retrieve metadata and the game session protection setting for one or more game sessions. 
   
  *  update-game-session – Change game session settings, such as maximum player count and join policy. 
   
  *  get-game-session-log-url – Get the location of saved logs for a game session. 
   

 
 
* **Manage player sessions**   

   
  *  create-player-session – Send a request for a player to join a game session. *Available in Amazon GameLift Local.*   
   
  *  create-player-sessions – Send a request for multiple players to join a game session. *Available in Amazon GameLift Local.*   
   
  *  describe-player-sessions – Get details on player activity, including status, playing time, and player data. *Available in Amazon GameLift Local.*   
   

 
 

 

 **Setting Up and Managing Game Servers**  

 

When setting up Amazon GameLift resources for your game, you first `create a game build <http://docs.aws.amazon.com/gamelift/latest/developerguide/gamelift-build-intro.html>`_ and upload it to Amazon GameLift. You can then use these actions to configure and manage a fleet of resources to run your game servers, scale capacity to meet player demand, access performance and utilization metrics, and more.

 

 
* **Manage game builds**   

   
  *  create-build – Create a new build using files stored in an Amazon S3 bucket. (Update uploading permissions with  request-upload-credentials .) To create a build and upload files from a local path, use the AWS CLI command ``upload-build`` . 
   
  *  list-builds – Get a list of all builds uploaded to a Amazon GameLift region. 
   
  *  describe-build – Retrieve information associated with a build. 
   
  *  update-build – Change build metadata, including build name and version. 
   
  *  delete-build – Remove a build from Amazon GameLift. 
   

 
 
* **Manage fleets**   

   
  *  create-fleet – Configure and activate a new fleet to run a build's game servers. 
   
  *  list-fleets – Get a list of all fleet IDs in a Amazon GameLift region (all statuses). 
   
  *  delete-fleet – Terminate a fleet that is no longer running game servers or hosting players. 
   
  * View / update fleet configurations. 

     
    *  describe-fleet-attributes /  update-fleet-attributes – View or change a fleet's metadata and settings for game session protection and resource creation limits. 
     
    *  describe-fleet-port-settings /  update-fleet-port-settings – View or change the inbound permissions (IP address and port setting ranges) allowed for a fleet. 
     
    *  describe-runtime-configuration /  update-runtime-configuration – View or change what server processes (and how many) to run on each instance in a fleet. 
     

   
   

 
 
* **Control fleet capacity**   

   
  *  describe-ec2-instance-limits – Retrieve maximum number of instances allowed for the current AWS account and the current usage level. 
   
  *  describe-fleet-capacity /  update-fleet-capacity – Retrieve the capacity settings and the current number of instances in a fleet; adjust fleet capacity settings to scale up or down. 
   
  * Autoscale – Manage autoscaling rules and apply them to a fleet. 

     
    *  put-scaling-policy – Create a new autoscaling policy, or update an existing one. 
     
    *  describe-scaling-policies – Retrieve an existing autoscaling policy. 
     
    *  delete-scaling-policy – Delete an autoscaling policy and stop it from affecting a fleet's capacity. 
     

   
   

 
 
* **Access fleet activity statistics**   

   
  *  describe-fleet-utilization – Get current data on the number of server processes, game sessions, and players currently active on a fleet. 
   
  *  describe-fleet-events – Get a fleet's logged events for a specified time span. 
   
  *  describe-game-sessions – Retrieve metadata associated with one or more game sessions, including length of time active and current player count. 
   

 
 
* **Remotely access an instance**   

   
  *  describe-instances – Get information on each instance in a fleet, including instance ID, IP address, and status. 
   
  *  get-instance-access – Request access credentials needed to remotely connect to a specified instance in a fleet. 
   

 
 
* **Manage fleet aliases**   

   
  *  create-alias – Define a new alias and optionally assign it to a fleet. 
   
  *  list-aliases – Get all fleet aliases defined in a Amazon GameLift region. 
   
  *  describe-alias – Retrieve information on an existing alias. 
   
  *  update-alias – Change settings for a alias, such as redirecting it from one fleet to another. 
   
  *  delete-alias – Remove an alias from the region. 
   
  *  resolve-alias – Get the fleet ID that a specified alias points to. 
   

 
 
* **Manage game session queues**   

   
  *  create-game-session-queue – Create a queue for processing requests for new game sessions.  
   
  *  describe-game-session-queues – Get data on all game session queues defined in a Amazon GameLift region. 
   
  *  update-game-session-queue – Change the configuration of a game session queue. 
   
  *  delete-game-session-queue – Remove a game session queue from the region. 
   

 
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  create-alias
  create-build
  create-fleet
  create-game-session
  create-game-session-queue
  create-player-session
  create-player-sessions
  delete-alias
  delete-build
  delete-fleet
  delete-game-session-queue
  delete-scaling-policy
  describe-alias
  describe-build
  describe-ec2-instance-limits
  describe-fleet-attributes
  describe-fleet-capacity
  describe-fleet-events
  describe-fleet-port-settings
  describe-fleet-utilization
  describe-game-session-details
  describe-game-session-placement
  describe-game-session-queues
  describe-game-sessions
  describe-instances
  describe-player-sessions
  describe-runtime-configuration
  describe-scaling-policies
  get-game-session-log
  get-game-session-log-url
  get-instance-access
  list-aliases
  list-builds
  list-fleets
  put-scaling-policy
  request-upload-credentials
  resolve-alias
  search-game-sessions
  start-game-session-placement
  stop-game-session-placement
  update-alias
  update-build
  update-fleet-attributes
  update-fleet-capacity
  update-fleet-port-settings
  update-game-session
  update-game-session-queue
  update-runtime-configuration
  upload-build
