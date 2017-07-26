[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-fleet-attributes:


*************************
describe-fleet-attributes
*************************



===========
Description
===========



Retrieves fleet properties, including metadata, status, and configuration, for one or more fleets. You can request attributes for all fleets, or specify a list of one or more fleet IDs. When requesting multiple fleets, use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  FleetAttributes object is returned for each requested fleet ID. When specifying a list of fleet IDs, attribute objects are returned only for fleets that currently exist. 

 

.. note::

   

  Some API actions may limit the number of fleet IDs allowed in one request. If a request exceeds this limit, the request fails and the error message includes the maximum allowed.

   

 

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
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeFleetAttributes>`_


========
Synopsis
========

::

    describe-fleet-attributes
  [--fleet-ids <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-ids`` (list)


  Unique identifier for a fleet(s) to retrieve attributes for. To request attributes for all fleets, leave this parameter empty.

  



Syntax::

  "string" "string" ...



``--limit`` (integer)


  Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages. This parameter is ignored when the request specifies one or a list of fleet IDs.

  

``--next-token`` (string)


  Token that indicates the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value. This parameter is ignored when the request specifies one or a list of fleet IDs.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FleetAttributes -> (list)

  

  Collection of objects containing attribute metadata for each requested fleet ID.

  

  (structure)

    

    General properties describing a fleet.

     

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

      

      Path to a game server executable in the fleet's build, specified for fleets created before 2016-08-04 (or AWS SDK v. 0.12.16). Server launch paths for fleets created after this date are specified in the fleet's  RuntimeConfiguration .

      

      

    ServerLaunchParameters -> (string)

      

      Game server launch parameters specified for fleets created before 2016-08-04 (or AWS SDK v. 0.12.16). Server launch parameters for fleets created after this date are specified in the fleet's  RuntimeConfiguration .

      

      

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

        

        

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

