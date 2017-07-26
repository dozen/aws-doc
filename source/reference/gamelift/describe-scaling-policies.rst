[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-scaling-policies:


*************************
describe-scaling-policies
*************************



===========
Description
===========



Retrieves all scaling policies applied to a fleet.

 

To get a fleet's scaling policies, specify the fleet ID. You can filter this request by policy status, such as to retrieve only active scaling policies. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, set of  ScalingPolicy objects is returned for the fleet.

 

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
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeScalingPolicies>`_


========
Synopsis
========

::

    describe-scaling-policies
  --fleet-id <value>
  [--status-filter <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet to retrieve scaling policies for.

  

``--status-filter`` (string)


  Scaling policy status to filter results on. A scaling policy is only in force when in an ``ACTIVE`` status.

   

   
  * **ACTIVE** – The scaling policy is currently in force. 
   
  * **UPDATEREQUESTED** – A request to update the scaling policy has been received. 
   
  * **UPDATING** – A change is being made to the scaling policy. 
   
  * **DELETEREQUESTED** – A request to delete the scaling policy has been received. 
   
  * **DELETING** – The scaling policy is being deleted. 
   
  * **DELETED** – The scaling policy has been deleted. 
   
  * **ERROR** – An error occurred in creating the policy. It should be removed and recreated. 
   

  

  Possible values:

  
  *   ``ACTIVE``

  
  *   ``UPDATE_REQUESTED``

  
  *   ``UPDATING``

  
  *   ``DELETE_REQUESTED``

  
  *   ``DELETING``

  
  *   ``DELETED``

  
  *   ``ERROR``

  

  

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

ScalingPolicies -> (list)

  

  Collection of objects containing the scaling policies matching the request.

  

  (structure)

    

    Rule that controls how a fleet is scaled. Scaling policies are uniquely identified by the combination of name and fleet ID.

     

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

      

      Unique identifier for a fleet that is associated with this scaling policy.

      

      

    Name -> (string)

      

      Descriptive label that is associated with a scaling policy. Policy names do not need to be unique.

      

      

    Status -> (string)

      

      Current status of the scaling policy. The scaling policy is only in force when in an ``ACTIVE`` status.

       

       
      * **ACTIVE** – The scaling policy is currently in force. 
       
      * **UPDATE_REQUESTED** – A request to update the scaling policy has been received. 
       
      * **UPDATING** – A change is being made to the scaling policy. 
       
      * **DELETE_REQUESTED** – A request to delete the scaling policy has been received. 
       
      * **DELETING** – The scaling policy is being deleted. 
       
      * **DELETED** – The scaling policy has been deleted. 
       
      * **ERROR** – An error occurred in creating the policy. It should be removed and recreated. 
       

      

      

    ScalingAdjustment -> (integer)

      

      Amount of adjustment to make, based on the scaling adjustment type.

      

      

    ScalingAdjustmentType -> (string)

      

      Type of adjustment to make to a fleet's instance count (see  FleetCapacity ):

       

       
      * **ChangeInCapacity** – add (or subtract) the scaling adjustment value from the current instance count. Positive values scale up while negative values scale down. 
       
      * **ExactCapacity** – set the instance count to the scaling adjustment value. 
       
      * **PercentChangeInCapacity** – increase or reduce the current instance count by the scaling adjustment, read as a percentage. Positive values scale up while negative values scale down. 
       

      

      

    ComparisonOperator -> (string)

      

      Comparison operator to use when measuring a metric against the threshold value.

      

      

    Threshold -> (double)

      

      Metric value used to trigger a scaling event.

      

      

    EvaluationPeriods -> (integer)

      

      Length of time (in minutes) the metric must be at or beyond the threshold before a scaling event is triggered.

      

      

    MetricName -> (string)

      

      Name of the Amazon GameLift-defined metric that is used to trigger an adjustment.

       

       
      * **ActivatingGameSessions** – number of game sessions in the process of being created (game session status = ``ACTIVATING`` ). 
       
      * **ActiveGameSessions** – number of game sessions currently running (game session status = ``ACTIVE`` ). 
       
      * **CurrentPlayerSessions** – number of active or reserved player sessions (player session status = ``ACTIVE`` or ``RESERVED`` ).  
       
      * **AvailablePlayerSessions** – number of player session slots currently available in active game sessions across the fleet, calculated by subtracting a game session's current player session count from its maximum player session count. This number does include game sessions that are not currently accepting players (game session ``PlayerSessionCreationPolicy`` = ``DENY_ALL`` ). 
       
      * **ActiveInstances** – number of instances currently running a game session. 
       
      * **IdleInstances** – number of instances not currently running a game session. 
       

      

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

