[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift put-scaling-policy:


******************
put-scaling-policy
******************



===========
Description
===========



Creates or updates a scaling policy for a fleet. An active scaling policy prompts Amazon GameLift to track a certain metric for a fleet and automatically change the fleet's capacity in specific circumstances. Each scaling policy contains one rule statement. Fleets can have multiple scaling policies in force simultaneously.

 

A scaling policy rule statement has the following structure:

 

If ``[MetricName]`` is ``[ComparisonOperator]``  ``[Threshold]`` for ``[EvaluationPeriods]`` minutes, then ``[ScalingAdjustmentType]`` to/by ``[ScalingAdjustment]`` .

 

For example, this policy: "If the number of idle instances exceeds 20 for more than 15 minutes, then reduce the fleet capacity by 10 instances" could be implemented as the following rule statement:

 

If [IdleInstances] is [GreaterThanOrEqualToThreshold] [20] for [15] minutes, then [ChangeInCapacity] by [-10].

 

To create or update a scaling policy, specify a unique combination of name and fleet ID, and set the rule values. All parameters for this action are required. If successful, the policy name is returned. Scaling policies cannot be suspended or made inactive. To stop enforcing a scaling policy, call  delete-scaling-policy .

 

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
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/PutScalingPolicy>`_


========
Synopsis
========

::

    put-scaling-policy
  --name <value>
  --fleet-id <value>
  --scaling-adjustment <value>
  --scaling-adjustment-type <value>
  --threshold <value>
  --comparison-operator <value>
  --evaluation-periods <value>
  --metric-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Descriptive label that is associated with a scaling policy. Policy names do not need to be unique. A fleet can have only one scaling policy with the same name.

  

``--fleet-id`` (string)


  Unique identifier for a fleet to apply this policy to.

  

``--scaling-adjustment`` (integer)


  Amount of adjustment to make, based on the scaling adjustment type.

  

``--scaling-adjustment-type`` (string)


  Type of adjustment to make to a fleet's instance count (see  FleetCapacity ):

   

   
  * **ChangeInCapacity** – add (or subtract) the scaling adjustment value from the current instance count. Positive values scale up while negative values scale down. 
   
  * **ExactCapacity** – set the instance count to the scaling adjustment value. 
   
  * **PercentChangeInCapacity** – increase or reduce the current instance count by the scaling adjustment, read as a percentage. Positive values scale up while negative values scale down; for example, a value of "-10" scales the fleet down by 10%. 
   

  

  Possible values:

  
  *   ``ChangeInCapacity``

  
  *   ``ExactCapacity``

  
  *   ``PercentChangeInCapacity``

  

  

``--threshold`` (double)


  Metric value used to trigger a scaling event.

  

``--comparison-operator`` (string)


  Comparison operator to use when measuring the metric against the threshold value.

  

  Possible values:

  
  *   ``GreaterThanOrEqualToThreshold``

  
  *   ``GreaterThanThreshold``

  
  *   ``LessThanThreshold``

  
  *   ``LessThanOrEqualToThreshold``

  

  

``--evaluation-periods`` (integer)


  Length of time (in minutes) the metric must be at or beyond the threshold before a scaling event is triggered.

  

``--metric-name`` (string)


  Name of the Amazon GameLift-defined metric that is used to trigger an adjustment.

   

   
  * **ActivatingGameSessions** – number of game sessions in the process of being created (game session status = ``ACTIVATING`` ). 
   
  * **ActiveGameSessions** – number of game sessions currently running (game session status = ``ACTIVE`` ). 
   
  * **CurrentPlayerSessions** – number of active or reserved player sessions (player session status = ``ACTIVE`` or ``RESERVED`` ).  
   
  * **AvailablePlayerSessions** – number of player session slots currently available in active game sessions across the fleet, calculated by subtracting a game session's current player session count from its maximum player session count. This number includes game sessions that are not currently accepting players (game session ``PlayerSessionCreationPolicy`` = ``DENY_ALL`` ). 
   
  * **ActiveInstances** – number of instances currently running a game session. 
   
  * **IdleInstances** – number of instances not currently running a game session. 
   

  

  Possible values:

  
  *   ``ActivatingGameSessions``

  
  *   ``ActiveGameSessions``

  
  *   ``ActiveInstances``

  
  *   ``AvailableGameSessions``

  
  *   ``AvailablePlayerSessions``

  
  *   ``CurrentPlayerSessions``

  
  *   ``IdleInstances``

  
  *   ``PercentAvailableGameSessions``

  
  *   ``PercentIdleInstances``

  
  *   ``QueueDepth``

  
  *   ``WaitTime``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Name -> (string)

  

  Descriptive label that is associated with a scaling policy. Policy names do not need to be unique.

  

  

