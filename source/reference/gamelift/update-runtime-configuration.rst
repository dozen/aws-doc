[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift update-runtime-configuration:


****************************
update-runtime-configuration
****************************



===========
Description
===========



Updates the current run-time configuration for the specified fleet, which tells Amazon GameLift how to launch server processes on instances in the fleet. You can update a fleet's run-time configuration at any time after the fleet is created; it does not need to be in an ``ACTIVE`` status.

 

To update run-time configuration, specify the fleet ID and provide a ``runtime-configuration`` object with the updated collection of server process configurations.

 

Each instance in a Amazon GameLift fleet checks regularly for an updated run-time configuration and changes how it launches server processes to comply with the latest version. Existing server processes are not affected by the update; they continue to run until they end, while Amazon GameLift simply adds new server processes to fit the current run-time configuration. As a result, the run-time configuration changes are applied gradually as existing processes shut down and new processes are launched in Amazon GameLift's normal process recycling activity.

 

Fleet-related operations include:

 

 
*  create-fleet   
 
*  list-fleets   
 
* Describe fleets: 

   
  *  describe-fleet-attributes   
   
  *  describe-fleet-port-settings   
   
  *  describe-fleet-utilization   
   
  *  describe-runtime-configuration   
   
  *  describe-fleet-events   
   

 
 
* Update fleets: 

   
  *  update-fleet-attributes   
   
  *  update-fleet-capacity   
   
  *  update-fleet-port-settings   
   
  *  update-runtime-configuration   
   

 
 
* Manage fleet capacity: 

   
  *  describe-fleet-capacity   
   
  *  update-fleet-capacity   
   
  *  put-scaling-policy (automatic scaling) 
   
  *  describe-scaling-policies (automatic scaling) 
   
  *  delete-scaling-policy (automatic scaling) 
   
  *  describe-ec2-instance-limits   
   

 
 
*  delete-fleet   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/UpdateRuntimeConfiguration>`_


========
Synopsis
========

::

    update-runtime-configuration
  --fleet-id <value>
  --runtime-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet to update run-time configuration for.

  

``--runtime-configuration`` (structure)


  Instructions for launching server processes on each instance in the fleet. The run-time configuration for a fleet has a collection of server process configurations, one for each type of server process to run on an instance. A server process configuration specifies the location of the server executable, launch parameters, and the number of concurrent processes with that configuration to maintain on each instance.

  



Shorthand Syntax::

    ServerProcesses=[{LaunchPath=string,Parameters=string,ConcurrentExecutions=integer},{LaunchPath=string,Parameters=string,ConcurrentExecutions=integer}],MaxConcurrentGameSessionActivations=integer,GameSessionActivationTimeoutSeconds=integer




JSON Syntax::

  {
    "ServerProcesses": [
      {
        "LaunchPath": "string",
        "Parameters": "string",
        "ConcurrentExecutions": integer
      }
      ...
    ],
    "MaxConcurrentGameSessionActivations": integer,
    "GameSessionActivationTimeoutSeconds": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

RuntimeConfiguration -> (structure)

  

  The run-time configuration currently in force. If the update was successful, this object matches the one in the request.

  

  ServerProcesses -> (list)

    

    Collection of server process configurations that describe which server processes to run on each instance in a fleet.

    

    (structure)

      

      A set of instructions for launching server processes on each instance in a fleet. Each instruction set identifies the location of the server executable, optional launch parameters, and the number of server processes with this configuration to maintain concurrently on the instance. Server process configurations make up a fleet's ``  runtime-configuration `` .

      

      LaunchPath -> (string)

        

        Location of the server executable in a game build. All game builds are installed on instances at the root : for Windows instances ``C:\game`` , and for Linux instances ``/local/game`` . A Windows game build with an executable file located at ``MyGame\latest\server.exe`` must have a launch path of "``C:\game\MyGame\latest\server.exe`` ". A Linux game build with an executable file located at ``MyGame/latest/server.exe`` must have a launch path of "``/local/game/MyGame/latest/server.exe`` ". 

        

        

      Parameters -> (string)

        

        Optional list of parameters to pass to the server executable on launch.

        

        

      ConcurrentExecutions -> (integer)

        

        Number of server processes using this configuration to run concurrently on an instance.

        

        

      

    

  MaxConcurrentGameSessionActivations -> (integer)

    

    Maximum number of game sessions with status ``ACTIVATING`` to allow on an instance simultaneously. This setting limits the amount of instance resources that can be used for new game activations at any one time.

    

    

  GameSessionActivationTimeoutSeconds -> (integer)

    

    Maximum amount of time (in seconds) that a game session can remain in status ``ACTIVATING`` . If the game session is not active before the timeout, activation is terminated and the game session status is changed to ``TERMINATED`` .

    

    

  

