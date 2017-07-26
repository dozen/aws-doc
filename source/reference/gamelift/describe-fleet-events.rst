[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-fleet-events:


*********************
describe-fleet-events
*********************



===========
Description
===========



Retrieves entries from the specified fleet's event log. You can specify a time range to limit the result set. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a collection of event log entries matching the request are returned.

 

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
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeFleetEvents>`_


========
Synopsis
========

::

    describe-fleet-events
  --fleet-id <value>
  [--start-time <value>]
  [--end-time <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet to get event logs for.

  

``--start-time`` (timestamp)


  Earliest date to retrieve event logs for. If no start time is specified, this call returns entries starting from when the fleet was created to the specified end time. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057").

  

``--end-time`` (timestamp)


  Most recent date to retrieve event logs for. If no end time is specified, this call returns entries from the specified start time up to the present. Format is a number expressed in Unix time as milliseconds (ex: "1469498468.057").

  

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

Events -> (list)

  

  Collection of objects containing event log entries for the specified fleet.

  

  (structure)

    

    Log entry describing an event that involves Amazon GameLift resources (such as a fleet). In addition to tracking activity, event codes and messages can provide additional information for troubleshooting and debugging problems.

    

    EventId -> (string)

      

      Unique identifier for a fleet event.

      

      

    ResourceId -> (string)

      

      Unique identifier for an event resource, such as a fleet ID.

      

      

    EventCode -> (string)

      

      Type of event being logged. The following events are currently in use:

       

       
      * General events: 

         
        * **GENERIC_EVENT** – An unspecified event has occurred. 
         

       
       
      * Fleet creation events: 

         
        * **FLEET_CREATED** – A fleet record was successfully created with a status of NEW. Event messaging includes the fleet ID. 
         
        * **FLEET_STATE_DOWNLOADING** – Fleet status changed from NEW to DOWNLOADING. The compressed build has started downloading to a fleet instance for installation. 
         
        * **FLEET_BINARY_DOWNLOAD_FAILED** – The build failed to download to the fleet instance. 
         
        * **FLEET_CREATION_EXTRACTING_BUILD** – The game server build was successfully downloaded to an instance, and the build files are now being extracted from the uploaded build and saved to an instance. Failure at this stage prevents a fleet from moving to ACTIVE status. Logs for this stage display a list of the files that are extracted and saved on the instance. Access the logs by using the URL in *PreSignedLogUrl* ). 
         
        * **FLEET_CREATION_RUNNING_INSTALLER** – The game server build files were successfully extracted, and the Amazon GameLift is now running the build's install script (if one is included). Failure in this stage prevents a fleet from moving to ACTIVE status. Logs for this stage list the installation steps and whether or not the install completed sucessfully. Access the logs by using the URL in *PreSignedLogUrl* ).  
         
        * **FLEET_CREATION_VALIDATING_RUNTIME_CONFIG** – The build process was successful, and the Amazon GameLift is now verifying that the game server launch path(s), which are specified in the fleet's run-time configuration, exist. If any listed launch path exists, Amazon GameLift tries to launch a game server process and waits for the process to report ready. Failures in this stage prevent a fleet from moving to ACTIVE status. Logs for this stage list the launch paths in the run-time configuration and indicate whether each is found. Access the logs by using the URL in *PreSignedLogUrl* ). Once the game server is launched, failures and crashes are logged; these logs can be downloaded from the Amazon GameLift console.  
         
        * **FLEET_STATE_VALIDATING** – Fleet status changed from DOWNLOADING to VALIDATING. 
         
        * **FLEET_VALIDATION_LAUNCH_PATH_NOT_FOUND** – Validation of the run-time validation failed because the executable specified in a launch path does not exist on the instance. 
         
        * **FLEET_STATE_BUILDING** – Fleet status changed from VALIDATING to BUILDING. 
         
        * **FLEET_VALIDATION_EXECUTABLE_RUNTIME_FAILURE** – Validation of the runtime validation failed because the executable specified in a launch path failed to run on the fleet instance. 
         
        * **FLEET_STATE_ACTIVATING** – Fleet status changed from BUILDING to ACTIVATING.  
         
        * **FLEET_ACTIVATION_FAILED** - The fleet failed to successfully complete one of the steps in the fleet activation process. This event code indicates that the game build was successfully downloaded to a fleet instance, built, and validated, but was not able to start a server process. A possible reason for failure is that the game server is not reporting "process ready" to the Amazon GameLift service. 
         
        * **FLEET_STATE_ACTIVE** – The fleet's status changed from ACTIVATING to ACTIVE. The fleet is now ready to host game sessions. 
         

       
       
      * Other fleet events: 

         
        * **FLEET_SCALING_EVENT** – A change was made to the fleet's capacity settings (desired instances, minimum/maximum scaling limits). Event messaging includes the new capacity settings. 
         
        * **FLEET_NEW_GAME_SESSION_PROTECTION_POLICY_UPDATED** – A change was made to the fleet's game session protection policy setting. Event messaging includes both the old and new policy setting.  
         
        * **FLEET_DELETED** – A request to delete a fleet was initiated. 
         

       
       

      

      

    Message -> (string)

      

      Additional information related to the event.

      

      

    EventTime -> (timestamp)

      

      Time stamp indicating when this event occurred. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

      

      

    PreSignedLogUrl -> (string)

      

      Location of stored logs with additional detail related to the event, useful for debugging issues. The URL is valid for 15 minutes. Fleet creation logs can also be accessed through the Amazon GameLift console.

      

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

