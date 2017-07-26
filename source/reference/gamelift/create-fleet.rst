[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift create-fleet:


************
create-fleet
************



===========
Description
===========



Creates a new fleet to run your game servers. A fleet is a set of Amazon Elastic Compute Cloud (Amazon EC2) instances, each of which can run multiple server processes to host game sessions. You configure a fleet to create instances with certain hardware specifications (see `Amazon EC2 Instance Types <http://aws.amazon.com/ec2/instance-types/>`_ for more information), and deploy a specified game build to each instance. A newly created fleet passes through several statuses; once it reaches the ``ACTIVE`` status, it can begin hosting game sessions.

 

To create a new fleet, you must specify the following: (1) fleet name, (2) build ID of an uploaded game build, (3) an EC2 instance type, and (4) a run-time configuration that describes which server processes to run on each instance in the fleet. (Although the run-time configuration is not a required parameter, the fleet cannot be successfully activated without it.)

 

You can also configure the new fleet with the following settings:

 

 
* Fleet description 
 
* Access permissions for inbound traffic 
 
* Fleetwide game session protection 
 
* Resource creation limit 
 

 

If you use Amazon CloudWatch for metrics, you can add the new fleet to a metric group. This allows you to view aggregated metrics for a set of fleets. Once you specify a metric group, the new fleet's metrics are included in the metric group's data.

 

If the create-fleet call is successful, Amazon GameLift performs the following tasks:

 

 
* Creates a fleet record and sets the status to ``NEW`` (followed by other statuses as the fleet is activated). 
 
* Sets the fleet's target capacity to 1 (desired instances), which causes Amazon GameLift to start one new EC2 instance. 
 
* Starts launching server processes on the instance. If the fleet is configured to run multiple server processes per instance, Amazon GameLift staggers each launch by a few seconds. 
 
* Begins writing events to the fleet event log, which can be accessed in the Amazon GameLift console. 
 
* Sets the fleet's status to ``ACTIVE`` as soon as one server process in the fleet is ready to host a game session. 
 

 

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
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/CreateFleet>`_


========
Synopsis
========

::

    create-fleet
  --name <value>
  [--description <value>]
  --build-id <value>
  [--server-launch-path <value>]
  [--server-launch-parameters <value>]
  [--log-paths <value>]
  --ec2-instance-type <value>
  [--ec2-inbound-permissions <value>]
  [--new-game-session-protection-policy <value>]
  [--runtime-configuration <value>]
  [--resource-creation-limit-policy <value>]
  [--metric-groups <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Descriptive label that is associated with a fleet. Fleet names do not need to be unique.

  

``--description`` (string)


  Human-readable description of a fleet.

  

``--build-id`` (string)


  Unique identifier for a build to be deployed on the new fleet. The build must have been successfully uploaded to Amazon GameLift and be in a ``READY`` status. This fleet setting cannot be changed once the fleet is created.

  

``--server-launch-path`` (string)


  This parameter is no longer used. Instead, specify a server launch path using the ``runtime-configuration`` parameter. (Requests that specify a server launch path and launch parameters instead of a run-time configuration will continue to work.)

  

``--server-launch-parameters`` (string)


  This parameter is no longer used. Instead, specify server launch parameters in the ``runtime-configuration`` parameter. (Requests that specify a server launch path and launch parameters instead of a run-time configuration will continue to work.)

  

``--log-paths`` (list)


  This parameter is no longer used. Instead, to specify where Amazon GameLift should store log files once a server process shuts down, use the Amazon GameLift server API ``ProcessReady()`` and specify one or more directory paths in ``logParameters`` . See more information in the `Server API Reference <http://docs.aws.amazon.com/gamelift/latest/developerguide/gamelift-sdk-server-api-ref.html#gamelift-sdk-server-api-ref-dataypes-process>`_ . 

  



Syntax::

  "string" "string" ...



``--ec2-instance-type`` (string)


  Name of an EC2 instance type that is supported in Amazon GameLift. A fleet instance type determines the computing resources of each instance in the fleet, including CPU, memory, storage, and networking capacity. Amazon GameLift supports the following EC2 instance types. See `Amazon EC2 Instance Types <http://aws.amazon.com/ec2/instance-types/>`_ for detailed descriptions.

  

  Possible values:

  
  *   ``t2.micro``

  
  *   ``t2.small``

  
  *   ``t2.medium``

  
  *   ``t2.large``

  
  *   ``c3.large``

  
  *   ``c3.xlarge``

  
  *   ``c3.2xlarge``

  
  *   ``c3.4xlarge``

  
  *   ``c3.8xlarge``

  
  *   ``c4.large``

  
  *   ``c4.xlarge``

  
  *   ``c4.2xlarge``

  
  *   ``c4.4xlarge``

  
  *   ``c4.8xlarge``

  
  *   ``r3.large``

  
  *   ``r3.xlarge``

  
  *   ``r3.2xlarge``

  
  *   ``r3.4xlarge``

  
  *   ``r3.8xlarge``

  
  *   ``m3.medium``

  
  *   ``m3.large``

  
  *   ``m3.xlarge``

  
  *   ``m3.2xlarge``

  
  *   ``m4.large``

  
  *   ``m4.xlarge``

  
  *   ``m4.2xlarge``

  
  *   ``m4.4xlarge``

  
  *   ``m4.10xlarge``

  

  

``--ec2-inbound-permissions`` (list)


  Range of IP addresses and port settings that permit inbound traffic to access server processes running on the fleet. If no inbound permissions are set, including both IP address range and port range, the server processes in the fleet cannot accept connections. You can specify one or more sets of permissions for a fleet.

  



Shorthand Syntax::

    FromPort=integer,ToPort=integer,IpRange=string,Protocol=string ...




JSON Syntax::

  [
    {
      "FromPort": integer,
      "ToPort": integer,
      "IpRange": "string",
      "Protocol": "TCP"|"UDP"
    }
    ...
  ]



``--new-game-session-protection-policy`` (string)


  Game session protection policy to apply to all instances in this fleet. If this parameter is not set, instances in this fleet default to no protection. You can change a fleet's protection policy using UpdateFleetAttributes, but this change will only affect sessions created after the policy change. You can also set protection for individual instances using  update-game-session .

   

   
  * **NoProtection** – The game session can be terminated during a scale-down event. 
   
  * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event. 
   

  

  Possible values:

  
  *   ``NoProtection``

  
  *   ``FullProtection``

  

  

``--runtime-configuration`` (structure)


  Instructions for launching server processes on each instance in the fleet. The run-time configuration for a fleet has a collection of server process configurations, one for each type of server process to run on an instance. A server process configuration specifies the location of the server executable, launch parameters, and the number of concurrent processes with that configuration to maintain on each instance. A create-fleet request must include a run-time configuration with at least one server process configuration; otherwise the request fails with an invalid request exception. (This parameter replaces the parameters ``ServerLaunchPath`` and ``ServerLaunchParameters`` ; requests that contain values for these parameters instead of a run-time configuration will continue to work.) 

  



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



``--resource-creation-limit-policy`` (structure)


  Policy that limits the number of game sessions an individual player can create over a span of time for this fleet.

  



Shorthand Syntax::

    NewGameSessionsPerCreator=integer,PolicyPeriodInMinutes=integer




JSON Syntax::

  {
    "NewGameSessionsPerCreator": integer,
    "PolicyPeriodInMinutes": integer
  }



``--metric-groups`` (list)


  Names of metric groups to add this fleet to. Use an existing metric group name to add this fleet to the group. Or use a new name to create a new metric group. A fleet can only be included in one metric group at a time.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FleetAttributes -> (structure)

  

  Properties for the newly created fleet.

  

  FleetId -> (string)

    

    Unique identifier for a fleet.

    

    

  FleetArn -> (string)

    

    Identifier for a fleet that is unique across all regions.

    

    

  Description -> (string)

    

    Human-readable description of the fleet.

    

    

  Name -> (string)

    

    Descriptive label that is associated with a fleet. Fleet names do not need to be unique.

    

    

  CreationTime -> (timestamp)

    

    Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

    

    

  TerminationTime -> (timestamp)

    

    Time stamp indicating when this data object was terminated. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

    

    

  Status -> (string)

    

    Current status of the fleet.

     

    Possible fleet statuses include the following:

     

     
    * **NEW** – A new fleet has been defined and desired instances is set to 1.  
     
    * **DOWNLOADING/VALIDATING/BUILDING/ACTIVATING** – Amazon GameLift is setting up the new fleet, creating new instances with the game build and starting server processes. 
     
    * **ACTIVE** – Hosts can now accept game sessions. 
     
    * **ERROR** – An error occurred when downloading, validating, building, or activating the fleet. 
     
    * **DELETING** – Hosts are responding to a delete fleet request. 
     
    * **TERMINATED** – The fleet no longer exists. 
     

    

    

  BuildId -> (string)

    

    Unique identifier for a build.

    

    

  ServerLaunchPath -> (string)

    

    Path to a game server executable in the fleet's build, specified for fleets created before 2016-08-04 (or AWS SDK v. 0.12.16). Server launch paths for fleets created after this date are specified in the fleet's  runtime-configuration .

    

    

  ServerLaunchParameters -> (string)

    

    Game server launch parameters specified for fleets created before 2016-08-04 (or AWS SDK v. 0.12.16). Server launch parameters for fleets created after this date are specified in the fleet's  runtime-configuration .

    

    

  LogPaths -> (list)

    

    Location of default log files. When a server process is shut down, Amazon GameLift captures and stores any log files in this location. These logs are in addition to game session logs; see more on game session logs in the `Amazon GameLift Developer Guide <http://docs.aws.amazon.com/gamelift/latest/developerguide/gamelift-sdk-server-api.html#gamelift-sdk-server-api-server-code>`_ . If no default log path for a fleet is specified, Amazon GameLift automatically uploads logs that are stored on each instance at ``C:\game\logs`` (for Windows) or ``/local/game/logs`` (for Linux). Use the Amazon GameLift console to access stored logs. 

    

    (string)

      

      

    

  NewGameSessionProtectionPolicy -> (string)

    

    Type of game session protection to set for all new instances started in the fleet.

     

     
    * **NoProtection** – The game session can be terminated during a scale-down event. 
     
    * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event. 
     

    

    

  OperatingSystem -> (string)

    

    Operating system of the fleet's computing resources. A fleet's operating system depends on the OS specified for the build that is deployed on this fleet.

    

    

  ResourceCreationLimitPolicy -> (structure)

    

    Fleet policy to limit the number of game sessions an individual player can create over a span of time.

    

    NewGameSessionsPerCreator -> (integer)

      

      Maximum number of game sessions that an individual can create during the policy period. 

      

      

    PolicyPeriodInMinutes -> (integer)

      

      Time span used in evaluating the resource creation limit policy. 

      

      

    

  MetricGroups -> (list)

    

    Names of metric groups that this fleet is included in. In Amazon CloudWatch, you can view metrics for an individual fleet or aggregated metrics for fleets that are in a fleet metric group. A fleet can be included in only one metric group at a time.

    

    (string)

      

      

    

  

