[ :ref:`aws <cli:aws>` ]

.. _cli:aws gamelift:


********
gamelift
********



===========
Description
===========

 

Welcome to the *Amazon GameLift API Reference* . Amazon GameLift is a managed Amazon Web Services (AWS) service for developers who need a scalable, server-based solution for multiplayer games. Amazon GameLift provides setup and deployment of game servers, and handles infrastructure scaling and session management. For more information about the GameLift service, including a feature overview, getting started guide, and tutorial, see the accompanying `Amazon GameLift Developer Guide`_ .

 

This reference describes the low-level service API for GameLift. You can call this API directly or use the `AWS SDK`_ for your preferred language. The AWS SDK includes a set of high-level GameLift actions multiplayer game sessions. Alternatively, you can use the `AWS command-line interface`_ (CLI) tool, which includes commands for GameLift. For administrative actions, you can use the Amazon GameLift console. 

 

**Setting Up Your Game Servers** 

 

Use these administrative actions to configure GameLift to host your game servers. When configuring GameLift, you'll need to (1) configure a build for your game and provide build files, and (2) set up one or more fleets to host game sessions.

 

 
* **Build actions:**  

   
  *  list-builds 
   
  *  create-build 
   
  *  describe-build 
   
  *  update-build 
   
  *  delete-build 
   
  *  request-upload-credentials 
   

 
 
* **Fleet actions:**  

   
  *  list-fleets 
   
  *  create-fleet 
   
  * Describe fleet actions: 

     
    *  describe-fleet-attributes 
     
    *  describe-fleet-capacity 
     
    *  describe-fleet-port-settings 
     
    *  describe-fleet-utilization 
     
    *  describe-ec2-instance-limits 
     
    *  describe-fleet-events 
     

   
   
  * Update fleet actions: 

     
    *  update-fleet-attributes 
     
    *  update-fleet-capacity 
     
    *  update-fleet-port-settings 
     

   
   
  *  delete-fleet 
   

 
 
* **Alias actions:**  

   
  *  list-aliases 
   
  *  create-alias 
   
  *  describe-alias 
   
  *  update-alias 
   
  *  delete-alias 
   
  *  resolve-alias 
   

 
 

 

**Managing Game and Player Sessions Through GameLift** 

 

Call these actions from your game clients and/or services to create and manage multiplayer game sessions.

 

 
* **Game sessions**  

   
  *  create-game-session 
   
  *  describe-game-sessions 
   
  *  update-game-session 
   

 
 
* **Player sessions**  

   
  *  create-player-session 
   
  *  create-player-sessions 
   
  *  describe-player-sessions 
   

 
 
* **Other actions:**  

   
  *  get-game-session-log-url 
   

 
 



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
  create-player-session
  create-player-sessions
  delete-alias
  delete-build
  delete-fleet
  describe-alias
  describe-build
  describe-ec2-instance-limits
  describe-fleet-attributes
  describe-fleet-capacity
  describe-fleet-events
  describe-fleet-port-settings
  describe-fleet-utilization
  describe-game-sessions
  describe-player-sessions
  get-game-session-log
  get-game-session-log-url
  list-aliases
  list-builds
  list-fleets
  request-upload-credentials
  resolve-alias
  update-alias
  update-build
  update-fleet-attributes
  update-fleet-capacity
  update-fleet-port-settings
  update-game-session
  upload-build


.. _Amazon GameLift Developer Guide: http://docs.aws.amazon.com/gamelift/latest/developerguide/
.. _AWS command-line interface: https://aws.amazon.com/cli/
.. _AWS SDK: https://aws.amazon.com/tools/
